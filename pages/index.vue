<template>
  <div class="min-h-screen bg-gradient-to-tr from-blue-100 via-white to-yellow-50 flex flex-col font-sans">
    <Navbar @open-attendance="showAttendance = true" />
    <!-- Hero Section -->
    <section class="flex-1 flex flex-col justify-center items-center text-center py-16 px-4 relative overflow-hidden">
      <transition name="fade-slide">
        <div>
          <h1 class="text-4xl md:text-6xl font-extrabold text-blue drop-shadow-lg mb-4 animate-fade-in">
            Camp Meeting 2025
          </h1>
          <h2 class="text-2xl md:text-4xl font-bold text-yellow-500 mb-2 animate-fade-in delay-200">
            "I Will Go"
          </h2>
          <p class="text-lg md:text-2xl text-black mb-6 animate-fade-in delay-400">
            Maximizing Opportunities for Wealth Creation
          </p>
          <div class="flex flex-col md:flex-row justify-center items-center gap-4 mb-6 animate-fade-in delay-600">
            <span class="bg-blue-100 text-yellow-600 px-4 py-2 rounded shadow font-semibold">2 Kings 4:1-7</span>
            <span class="bg-blue-100 text-yellow-600 px-4 py-2 rounded shadow font-semibold">Hymnal 88, Nzk 38</span>
          </div>
          <div class="mb-8 animate-fade-in delay-800">
            <span
              class="inline-block bg-blue-900 bg-opacity-90 text-white text-xl md:text-2xl font-bold px-6 py-2 rounded shadow">
              17-23 AUG 2025
            </span>
            <span class="block text-yellow-500 font-bold text-lg md:text-xl mt-2">Mustard Seed Academy</span>
          </div>
          <div class="flex flex-col md:flex-row gap-4 justify-center items-center mt-4">
            <a href="#register"
              class="inline-block px-8 py-3 bg-yellow-400 text-blue-900 font-bold rounded-full shadow-lg hover:bg-yellow-300 transition-all duration-300 animate-bounce">
              Register Now
            </a>
            <button @click="showAttendance = true"
              class="inline-block px-8 py-3 bg-blue-900 text-white font-bold rounded-full shadow-lg hover:bg-blue-700 transition-all duration-300 animate-bounce">
              Attendance
            </button>
          </div>
        </div>
      </transition>
      <!-- Animated background shapes -->
      <div
        class="absolute top-0 left-0 w-64 h-64 bg-yellow-200 bg-opacity-30 rounded-full blur-3xl animate-pulse -z-10">
      </div>
      <div
        class="absolute bottom-0 right-0 w-80 h-80 bg-blue-200 bg-opacity-30 rounded-full blur-3xl animate-pulse -z-10">
      </div>
    </section>
    <!-- About Section -->
    <section class="max-w-3xl mx-auto py-12 px-4 text-center animate-fade-in delay-1000">
      <h3 class="text-2xl md:text-3xl font-bold text-blue-900 mb-4">About the Camp Meeting</h3>
      <p class="text-lg text-black mb-2">
        Join us for a life-changing spiritual experience at the 2025 SDA Camp Meeting! This year, our focus is on
        empowering individuals and families to maximize opportunities for wealth creation, spiritual growth, and
        community service. All are welcome—come and be blessed!
      </p>
    </section>
    <!-- Speakers Section -->
    <section class="max-w-5xl mx-auto py-12 px-4 animate-fade-in delay-1200">
      <h3 class="text-2xl md:text-3xl font-bold text-blue-900 mb-8 text-center">Featured Speakers</h3>
      <div class="grid grid-cols-1 md:grid-cols-4 gap-8">
        <div class="flex flex-col items-center group transition-transform duration-300 hover:-translate-y-2">
          <img src="/images/maxwell.jpg" alt="Pr. Maxwell Kemboi"
            class="w-32 h-32 rounded-full shadow-lg border-4 border-yellow-400 mb-3 group-hover:scale-105 transition-transform duration-300" />
          <span class="font-bold text-blue-900">Pr. Maxwell Kemboi</span>
          <span class="text-yellow-600 text-sm">Guest Speaker</span>
        </div>
        <div class="flex flex-col items-center group transition-transform duration-300 hover:-translate-y-2">
          <img src="/images/yego.jpg" alt="Mrs. Yego"
            class="w-32 h-32 rounded-full shadow-lg border-4 border-yellow-400 mb-3 group-hover:scale-105 transition-transform duration-300" />
          <span class="font-bold text-blue-900">Mrs. Yego</span>
          <span class="text-yellow-600 text-sm">2nd Speaker</span>
        </div>
        <div class="flex flex-col items-center group transition-transform duration-300 hover:-translate-y-2">
          <img src="/images/brotherson.jpg" alt="Brotherson"
            class="w-32 h-32 rounded-full shadow-lg border-4 border-yellow-400 mb-3 group-hover:scale-105 transition-transform duration-300" />
          <span class="font-bold text-blue-900">Brotherson</span>
          <span class="text-yellow-600 text-sm">2nd Speaker</span>
        </div>
        <div class="flex flex-col items-center group transition-transform duration-300 hover:-translate-y-2">
          <img src="/images/ptarus.jpg" alt="Pr. Joseph Tarus"
            class="w-32 h-32 rounded-full shadow-lg border-4 border-yellow-400 mb-3 group-hover:scale-105 transition-transform duration-300" />
          <span class="font-bold text-blue-900">Pr. Joseph Tarus</span>
          <span class="text-yellow-600 text-sm">Host Pastor</span>
        </div>
      </div>
    </section>
    <!-- Program Highlights Section -->
    <section class="max-w-4xl mx-auto py-12 px-4 animate-fade-in delay-1400">
      <h3 class="text-2xl md:text-3xl font-bold text-blue-900 mb-8 text-center">Program Highlights</h3>
      <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
        <div
          class="bg-white bg-opacity-90 rounded-xl shadow-lg p-6 flex flex-col items-center hover:shadow-2xl transition-shadow duration-300 animate-fade-in delay-1500">
          <span class="text-4xl mb-2">🎤</span>
          <span class="font-bold text-blue-900 mb-1">Inspiring Sermons</span>
          <span class="text-black text-sm">Daily messages from dynamic speakers to uplift your spirit.</span>
        </div>
        <div
          class="bg-white bg-opacity-90 rounded-xl shadow-lg p-6 flex flex-col items-center hover:shadow-2xl transition-shadow duration-300 animate-fade-in delay-1600">
          <span class="text-4xl mb-2">🎶</span>
          <span class="font-bold text-blue-900 mb-1">Music & Choirs</span>
          <span class="text-black text-sm">Enjoy uplifting music, choirs, and special performances.</span>
        </div>
        <div
          class="bg-white bg-opacity-90 rounded-xl shadow-lg p-6 flex flex-col items-center hover:shadow-2xl transition-shadow duration-300 animate-fade-in delay-1700">
          <span class="text-4xl mb-2">🧒</span>
          <span class="font-bold text-blue-900 mb-1">Youth & Children</span>
          <span class="text-black text-sm">Special programs for youth and children throughout the week.</span>
        </div>
      </div>
    </section>
    <!-- Contact & Registration Section -->
    <section id="register" class="max-w-2xl mx-auto py-12 px-4 text-center animate-fade-in delay-1800">
      <h3 class="text-2xl md:text-3xl font-bold text-blue-900 mb-4">Contact & Registration</h3>
      <p class="text-black mb-2">For more information, contact Elder Maiyo: <a href="tel:0722909012"
          class="text-yellow-600 underline">0722909012</a></p>
      <a href="#"
        class="inline-block mt-4 px-8 py-3 bg-blue-900 text-yellow-300 font-bold rounded-full shadow-lg hover:bg-blue-700 transition-all duration-300">Register
        Your Interest</a>
      <div class="mt-6 text-blue-700 text-sm">www.kabongwacamp2025.vercel.app</div>
    </section>
    <!-- Footer -->
    <footer class="py-6 text-center text-blue-900 bg-white bg-opacity-80 mt-auto animate-fade-in delay-2000">
      <a href="/wrvf-camp-material.pdf" download
        class="inline-block mt-6 px-8 py-3 bg-yellow-400 text-blue-900 font-bold rounded-full shadow-lg hover:bg-yellow-300 transition-all duration-300 text-lg">
        <svg class="inline-block w-6 h-6 mr-2 align-middle" fill="none" stroke="currentColor" stroke-width="2"
          viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" d="M12 4v12m0 0l-4-4m4 4l4-4m-8 8h8" />
        </svg>
        Download Camp Material (PDF)
      </a>
      <div>© 2025 Kabongwa & Kapchemoiyo SDA Camp Meeting. All rights reserved.</div>

    </footer>
    <AttendanceModal :show="showAttendance" @close="showAttendance = false" />
  </div>
</template>

<script setup>
import { ref } from 'vue';

useHead({
  title: 'Kabongwa Kapchemoiywo Camp Meeting 2025',
  meta: [
    { name: 'description', content: 'KABONGWA KAPCHEMOIYWO CAMP MEETING 2025' },
    { property: 'og:title', content: 'Kabongwa Kapchemoiywo Camp Meeting 2025' },
    { property: 'og:description', content: 'KABONGWA KAPCHEMOIYWO CAM MEETING 2025' },
    { property: 'og:image', content: '/images/preview.jpg' },
    { property: 'og:type', content: 'website' },
    { name: 'twitter:card', content: 'summary_large_image' },
    { name: 'twitter:title', content: 'Kabongwa Kapchemoiywo Camp Meeting 2025' },
    { name: 'twitter:description', content: 'KABONGWA KAPCHEMOIYWO CAMP MEETING 2025' },
    { name: 'twitter:image', content: '/images/preview.jpg' }
  ]
});
const showAttendance = ref(false);
</script>

<style scoped>
@keyframes fade-in {
  from { opacity: 0; transform: translateY(30px); }
  to { opacity: 1; transform: translateY(0); }
}
.animate-fade-in {
  animation: fade-in 1s cubic-bezier(0.4,0,0.2,1) both;
}
.animate-fade-in.delay-200 { animation-delay: 0.2s; }
.animate-fade-in.delay-400 { animation-delay: 0.4s; }
.animate-fade-in.delay-600 { animation-delay: 0.6s; }
.animate-fade-in.delay-800 { animation-delay: 0.8s; }
.animate-fade-in.delay-1000 { animation-delay: 1s; }
.animate-fade-in.delay-1200 { animation-delay: 1.2s; }
.animate-fade-in.delay-1400 { animation-delay: 1.4s; }
.animate-fade-in.delay-1500 { animation-delay: 1.5s; }
.animate-fade-in.delay-1600 { animation-delay: 1.6s; }
.animate-fade-in.delay-1700 { animation-delay: 1.7s; }
.animate-fade-in.delay-1800 { animation-delay: 1.8s; }
.animate-fade-in.delay-2000 { animation-delay: 2s; }

.fade-slide-enter-active, .fade-slide-leave-active {
  transition: opacity 0.8s, transform 0.8s;
}
.fade-slide-enter-from, .fade-slide-leave-to {
  opacity: 0;
  transform: translateY(40px);
}
.fade-slide-enter-to, .fade-slide-leave-from {
  opacity: 1;
  transform: translateY(0);
}
</style>