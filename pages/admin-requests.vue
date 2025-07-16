<template>
  <div class="min-h-screen bg-gradient-to-tr from-blue-100 via-white to-yellow-50 flex flex-col font-sans">
    <Navbar />
    <div class="flex-1 flex flex-col justify-center items-center py-16 px-4">
      <div class="max-w-3xl w-full">
        <h1 class="text-3xl font-bold text-blue-900 mb-6 text-center">All Prayer Requests</h1>
        <div v-if="loading" class="text-center text-blue-700">Loading...</div>
        <table v-else class="w-full bg-white rounded shadow-lg">
          <thead>
            <tr class="bg-blue-100 text-blue-900">
              <th class="py-2 px-4">Name</th>
              <th class="py-2 px-4">Request</th>
              <th class="py-2 px-4">Contact</th>
              <th class="py-2 px-4">Date</th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="req in requests" :key="req.id" class="border-b">
              <td class="py-2 px-4">{{ req.name }}</td>
              <td class="py-2 px-4">{{ req.request }}</td>
              <td class="py-2 px-4">{{ req.contact }}</td>
              <td class="py-2 px-4">{{ new Date(req.created_at).toLocaleString() }}</td>
            </tr>
          </tbody>
        </table>
        <div v-if="requests.length === 0 && !loading" class="text-center text-gray-500 mt-6">No requests yet.</div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import Navbar from '../components/Navbar.vue';
import { ref, onMounted } from 'vue';
import { supabase } from '../server/utils/supabase';

const requests = ref<any[]>([]);
const loading = ref(true);

onMounted(async () => {
  const { data, error } = await supabase.from('prayer_requests').select('*').order('created_at', { ascending: false });
  if (!error && data) {
    requests.value = data;
  }
  loading.value = false;
});
</script>