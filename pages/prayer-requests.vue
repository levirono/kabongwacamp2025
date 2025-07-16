<template>
  <div class="min-h-screen bg-gradient-to-tr from-blue-100 via-white to-yellow-50 flex flex-col font-sans">
    <Navbar />
    <div class="flex-1 flex flex-col justify-center items-center py-16 px-4">
      <div class="max-w-xl w-full">
        <h1 class="text-3xl font-bold text-blue-900 mb-6 text-center">Submit a Prayer Request</h1>
        <form @submit.prevent="submitRequest" class="bg-white rounded-lg shadow-lg p-6 flex flex-col gap-4">
          <input v-model="name" type="text" placeholder="Your Name" class="border rounded px-4 py-2" required />
          <textarea v-model="request" placeholder="Your Prayer Request" class="border rounded px-4 py-2" rows="4"
            required></textarea>
          <input v-model="contact" type="text" placeholder="Contact (optional)" class="border rounded px-4 py-2" />
          <button type="submit" :disabled="submitting"
            class="bg-blue-900 text-white font-bold px-6 py-2 rounded hover:bg-blue-700 transition">
            <span v-if="submitting">Submitting...</span>
            <span v-else>Submit</span>
          </button>
          <div v-if="success" class="text-green-600 mt-2">Thank you! Your request has been submitted.</div>
          <div v-if="error" class="text-red-600 mt-2">There was an error. Please try again.</div>
        </form>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import Navbar from '../components/Navbar.vue';
import { ref } from 'vue';
import { supabase } from '../server/utils/supabase';

const name = ref('');
const request = ref('');
const contact = ref('');
const success = ref(false);
const error = ref(false);
const submitting = ref(false);

const submitRequest = async () => {
  success.value = false;
  error.value = false;
  submitting.value = true;
  const { error: supaError } = await supabase.from('prayer_requests').insert([
    { name: name.value, request: request.value, contact: contact.value }
  ]);
  submitting.value = false;
  if (supaError) {
    error.value = true;
  } else {
    success.value = true;
    name.value = '';
    request.value = '';
    contact.value = '';
    setTimeout(() => {
      success.value = false;
    }, 3000);
  }
};
</script>

<style>
/* Add any additional global styles here if needed */
</style>