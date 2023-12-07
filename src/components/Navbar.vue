<script setup>
import { ref } from "vue";

const isMobileMenuOpen = ref(false);

const toggleMobileMenu = () => {
  isMobileMenuOpen.value = !isMobileMenuOpen.value;
};
</script>

<template>
  <header class="py-4 drop-shadow-lg box-shadow-lg shadow-lg">
    <div class="flex justify-between items-center max-w-6xl mx-auto p-3">
      <a href="#/">
        <img alt="Vue logo" class="w-24" src="/src/assets/archintel-logo.gif" />
      </a>

      <!-- Mobile Menu Button -->
      <button
        @click="toggleMobileMenu"
        class="lg:hidden text-gray-800 focus:outline-none"
      >
        <svg
          class="w-6 h-6"
          fill="none"
          stroke="currentColor"
          viewBox="0 0 24 24"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M4 6h16M4 12h16m-7 6h7"
          ></path>
        </svg>
      </button>

      <!-- Mobile Menu -->
      <div
        :class="{ hidden: !isMobileMenuOpen }"
        class="lg:hidden flex flex-col gap-4 items-end absolute top-full right-0 bg-white p-4 rounded-md shadow-md"
      >
        <a href="https://archintel.com/" class="text-slate-700 hover:underline"
          >About Us</a
        >
        <a href="#" class="text-slate-700 hover:underline">Articles</a>
        <a
          href="#/login"
          class="bg-sky-700 text-white font-medium py-2 items-center text-sm px-6 rounded-full"
        >
          Login
        </a>
      </div>

      <!-- Desktop Menu -->
      <div class="hidden lg:flex gap-6 items-center cursor-pointer">
        <ul class="flex gap-5">
          <a
            href="https://archintel.com/"
            class="text-slate-700 hover:underline"
            >About Us</a
          >
          <a href="#" class="text-slate-700 hover:underline">Articles</a>
        </ul>
        <a
          href="#/login"
          class="bg-sky-700 text-white font-medium py-2 items-center text-sm px-6 rounded-full"
        >
          Login
        </a>
      </div>
    </div>
  </header>
</template>
