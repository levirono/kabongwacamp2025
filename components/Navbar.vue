<template>
    <nav class="bg-white/80 shadow-md py-3 px-6 flex flex-wrap items-center justify-between">
      <!-- Logo / Title -->
      <div class="text-xl font-extrabold text-blue-900 tracking-wide">
        Camp Meeting 2025
      </div>
  
      <!-- Navigation Links -->
      <div class="flex flex-wrap items-center gap-3 mt-2 sm:mt-0">
        <NuxtLink
          to="/"
          class="px-3 py-2 rounded transition hover:bg-blue-100"
          :class="{ 'text-yellow-600 font-bold': $route.path === '/', 'text-blue-900': $route.path !== '/' }"
        >
          Home
        </NuxtLink>
  
        <NuxtLink
          to="/prayer-requests"
          class="px-3 py-2 rounded transition hover:bg-blue-100"
          :class="{ 'text-yellow-600 font-bold': $route.path === '/prayer-requests', 'text-blue-900': $route.path !== '/prayer-requests' }"
        >
          Prayer Requests
        </NuxtLink>
  
        <NuxtLink
          to="/camp-offerings"
          class="px-3 py-2 rounded transition hover:bg-blue-100"
          :class="{ 'text-yellow-600 font-bold': $route.path === '/camp-offerings', 'text-blue-900': $route.path !== '/camp-offerings' }"
        >
          Camp Offerings
        </NuxtLink>
  
        <!-- Attendance Button -->
        <button
          @click="$emit('open-attendance')"
          class="bg-blue-900 text-white px-4 py-2 rounded hover:bg-blue-700 transition font-semibold"
        >
          Attendance
        </button>
      </div>
    </nav>
  </template>
  
  <script setup>
  // No script needed unless you plan to handle logic
  </script>
  