<script setup>
import { ref } from "vue";
import { globalState } from "@/store";

const isMobileMenuOpen = ref(false);
const dropdownVisible = ref(false);

const toggleMobileMenu = () => {
  isMobileMenuOpen.value = !isMobileMenuOpen.value;
};

const toggleDropdown = () => {
  dropdownVisible.value = !dropdownVisible.value;
};

const logout = () => {
  // Add your logout logic here
  console.log("Logout clicked");
  // You can redirect to a login page or perform other logout actions here
  // Example: window.location.href = '/login';
};
</script>

<template>
  <header class="py-4 drop-shadow-lg box-shadow-lg shadow-lg">
    <div class="flex gap-4 justify-between items-center max-w-6xl mx-auto p-3">
      <!-- Mobile Menu Button -->
      {{ globalState.user }}

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

      <div class="lg:flex gap-16">
        <!-- Logo -->
        <a href="#/">
          <img
            alt="Vue logo"
            class="w-24"
            src="/src/assets/archintel-logo.gif"
          />
        </a>

        <!-- Desktop Menu -->
        <ul class="hidden lg:flex gap-8">
          <a
            href="#/dashboard"
            class="hover:underline duration-500 transition-all"
            >Dashboard</a
          >
          <a
            href="#/articles-table"
            class="hover:underline duration-500 transition-all"
            >All Media</a
          >
          <a
            href="#/users-list"
            class="hover:underline duration-500 transition-all"
            >Users</a
          >
          <a
            href="#/company-list"
            class="hover:underline duration-500 transition-all"
            >Companies</a
          >
        </ul>
      </div>

      <!-- Mobile Menu -->
      <div
        :class="{ hidden: !isMobileMenuOpen }"
        class="lg:hidden flex flex-col gap-4 items-end absolute top-full left-0 bg-white p-4 rounded-md shadow-md"
      >
        <a
          href="#/dashboard"
          class="hover:underline duration-500 transition-all"
          >Dashboard</a
        >
        <a
          href="#/articles-table"
          class="hover:underline duration-500 transition-all"
          >All Media</a
        >
        <a
          href="#/users-list"
          class="hover:underline duration-500 transition-all"
          >Users</a
        >
        <a
          href="#/company-list"
          class="hover:underline duration-500 transition-all"
          >Companies</a
        >
      </div>

      <!-- User Profile -->
      <div class="flex gap-6 items-center cursor-pointer lg:flex">
        <div class="hidden sm:block">
          <h3 class="text-slate-700 font-semibold">Leonora Hale</h3>
          <h4>Editor</h4>
        </div>
        <div @click="toggleDropdown" class="relative">
          <div class="rounded-full h-12 w-12">
            <img
              class="w-12 h-12 rounded-full mx-auto object-cover"
              src="/src/assets/sample-img.jpg"
              alt="profile-image"
            />
          </div>
          <!-- Logout Dropdown -->
          <div
            v-show="dropdownVisible"
            @click="logout"
            class="absolute right-0 mt-2 w-48 bg-white border border-gray-300 rounded-md shadow-md overflow-hidden"
            style="display: none"
          >
            <a
              href="#"
              class="block px-4 py-2 text-sm text-red-600 hover:bg-gray-100 cursor-pointer"
              >Logout</a
            >
          </div>
        </div>
      </div>
    </div>
  </header>
</template>
