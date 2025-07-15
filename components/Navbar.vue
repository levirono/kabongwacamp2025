<template>
    <nav class="bg-white/80 shadow-md py-3 px-6 flex items-center justify-between">
      <!-- Logo / Title (hidden on mobile) -->
      <div class="text-xl font-extrabold text-blue-900 tracking-wide hidden sm:block">
        Camp Meeting 2025
      </div>
  
      <!-- Hamburger for mobile -->
      <button
        @click="menuOpen = !menuOpen"
        class="sm:hidden text-blue-900 focus:outline-none"
        aria-label="Open menu"
      >
        <svg class="w-8 h-8" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M4 6h16M4 12h16M4 18h16"
          />
        </svg>
      </button>
  
      <!-- Navigation Links (desktop) -->
      <div class="flex flex-wrap items-center gap-3 mt-2 sm:mt-0 hidden sm:flex">
        <NuxtLink
          to="/"
          class="px-3 py-2 rounded transition hover:bg-blue-100"
          :class="{
            'text-yellow-600 font-bold': $route.path === '/',
            'text-blue-900': $route.path !== '/',
          }"
        >
          Home
        </NuxtLink>
  
        <NuxtLink
          to="/prayer-requests"
          class="px-3 py-2 rounded transition hover:bg-blue-100"
          :class="{
            'text-yellow-600 font-bold': $route.path === '/prayer-requests',
            'text-blue-900': $route.path !== '/prayer-requests',
          }"
        >
          Prayer Requests
        </NuxtLink>
  
        <NuxtLink
          to="/camp-offerings"
          class="px-3 py-2 rounded transition hover:bg-blue-100"
          :class="{
            'text-yellow-600 font-bold': $route.path === '/camp-offerings',
            'text-blue-900': $route.path !== '/camp-offerings',
          }"
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
  
      <!-- Mobile Menu Dropdown -->
      <div
        v-if="menuOpen"
        class="absolute top-16 left-0 w-full bg-white/95 shadow-lg flex flex-col items-center gap-3 py-4 sm:hidden z-50"
      >
        <NuxtLink
          to="/"
          class="px-3 py-2 rounded transition hover:bg-blue-100 w-full text-center"
          :class="{
            'text-yellow-600 font-bold': $route.path === '/',
            'text-blue-900': $route.path !== '/',
          }"
          @click="menuOpen = false"
        >
          Home
        </NuxtLink>
        <NuxtLink
          to="/prayer-requests"
          class="px-3 py-2 rounded transition hover:bg-blue-100 w-full text-center"
          :class="{
            'text-yellow-600 font-bold': $route.path === '/prayer-requests',
            'text-blue-900': $route.path !== '/prayer-requests',
          }"
          @click="menuOpen = false"
        >
          Prayer Requests
        </NuxtLink>
        <NuxtLink
          to="/camp-offerings"
          class="px-3 py-2 rounded transition hover:bg-blue-100 w-full text-center"
          :class="{
            'text-yellow-600 font-bold': $route.path === '/camp-offerings',
            'text-blue-900': $route.path !== '/camp-offerings',
          }"
          @click="menuOpen = false"
        >
          Camp Offerings
        </NuxtLink>
        <button
          @click="$emit('open-attendance'); menuOpen = false"
          class="bg-blue-900 text-white px-4 py-2 rounded hover:bg-blue-700 transition font-semibold w-full"
        >
          Attendance
        </button>
      </div>
    </nav>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  const menuOpen = ref(false);
  </script>
