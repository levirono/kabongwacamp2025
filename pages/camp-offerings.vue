<template>
  <div class="min-h-screen bg-gradient-to-tr from-blue-100 via-white to-yellow-50 flex flex-col font-sans">
    <Navbar />
    <div class="flex-1 flex flex-col justify-center items-center py-16 px-4">
      <div class="max-w-xl w-full flex items-center justify-center" style="height: 60vh;">
        <h1 class="text-4xl md:text-6xl font-extrabold text-blue-900 text-center">Contents will be made available soon
        </h1>
      </div>
      <!--
      <div class="max-w-xl w-full">
        <h1 class="text-3xl font-bold text-blue-900 mb-6 text-center">Camp Offerings</h1>
        <form @submit.prevent="submitOffering" class="bg-white rounded-lg shadow-lg p-6 flex flex-col gap-4">
          <input v-model="name" type="text" placeholder="Your Name" class="border rounded px-4 py-2" required />
          <input v-model="amount" type="number" min="1" placeholder="Amount (KES)" class="border rounded px-4 py-2" required />
          <textarea v-model="message" placeholder="Message (optional)" class="border rounded px-4 py-2" rows="2"></textarea>
          <button type="submit" class="bg-yellow-400 text-blue-900 font-bold px-6 py-2 rounded hover:bg-yellow-300 transition">Submit Offering</button>
          <div v-if="success" class="text-green-600 mt-2">Thank you for your offering!</div>
          <div v-if="error" class="text-red-600 mt-2">There was an error. Please try again.</div>
        </form>
      </div>
      -->
    </div>
  </div>
</template>

<script setup lang="ts">
import Navbar from '../components/Navbar.vue';
//
// const name = ref('');
// const amount = ref('');
// const message = ref('');
// const success = ref(false);
// const error = ref(false);
//
// const submitOffering = async () => {
//   success.value = false;
//   error.value = false;
//   const { error: supaError } = await supabase.from('camp_offerings').insert([
//     { name: name.value, amount: amount.value, message: message.value }
//   ]);
//   if (supaError) {
//     error.value = true;
//   } else {
//     success.value = true;
//     name.value = '';
//     amount.value = '';
//     message.value = '';
//   }
// };
</script>

<style>
/* Add any additional global styles here if needed */
</style>