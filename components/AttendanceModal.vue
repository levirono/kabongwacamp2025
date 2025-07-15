<template>
  <div v-if="show" class="fixed inset-0 bg-black bg-opacity-40 flex items-center justify-center z-50">
    <div class="bg-white rounded-lg shadow-xl p-8 w-full max-w-md relative animate-fade-in">
      <button @click="$emit('close')" class="absolute top-2 right-2 text-gray-400 hover:text-gray-700 text-2xl">&times;</button>
      <h2 class="text-2xl font-bold text-blue-900 mb-4 text-center">Will You Attend?</h2>
      <form @submit.prevent="submitAttendance" class="flex flex-col gap-4">
        <input v-model="name" type="text" placeholder="Your Name" class="border rounded px-4 py-2" required />
        <input v-model="contact" type="text" placeholder="Contact (phone/email)" class="border rounded px-4 py-2" required />
        <div class="flex gap-4 items-center justify-center">
          <label class="flex items-center gap-2">
            <input type="radio" value="yes" v-model="attending" required />
            <span>Yes</span>
          </label>
          <label class="flex items-center gap-2">
            <input type="radio" value="no" v-model="attending" required />
            <span>No</span>
          </label>
        </div>
        <button type="submit" class="bg-blue-900 text-white font-bold px-6 py-2 rounded hover:bg-blue-700 transition">Submit</button>
        <div v-if="success" class="text-green-600 mt-2">Thank you for your response!</div>
        <div v-if="error" class="text-red-600 mt-2">There was an error. Please try again.</div>
      </form>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref, defineProps, defineEmits } from 'vue';
const props = defineProps<{ show: boolean }>();
const emit = defineEmits(['close']);
// import supabase utility

const name = ref('');
const contact = ref('');
const attending = ref('');
const success = ref(false);
const error = ref(false);

const submitAttendance = async () => {
  success.value = false;
  error.value = false;
  const { error: supaError } = await supabase.from('attendance').insert([
    { name: name.value, contact: contact.value, attending: attending.value }
  ]);
  if (supaError) {
    error.value = true;
  } else {
    success.value = true;
    name.value = '';
    contact.value = '';
    attending.value = '';
    setTimeout(() => emit('close'), 1200);
  }
};
</script> 