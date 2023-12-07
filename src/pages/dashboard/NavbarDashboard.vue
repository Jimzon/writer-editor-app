<script setup></script>

<template>
  <header class="py-4 drop-shadow-lg box-shadow-lg shadow-lg">
    <div class="flex gap-4 justify-between items-center max-w-6xl mx-auto p-3">
      <div class="flex gap-16">
        <a href="#/">
          <img
            alt="Vue logo"
            class="w-24"
            src="/src/assets/archintel-logo.gif"
          />
        </a>

        <ul class="flex gap-8">
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
        </ul>
      </div>

      <div class="flex gap-6 items-center cursor-pointer">
        <div class="block">
          <h3 class="text-slate-700 font-semibold">Leonora Hale</h3>
          <h4>Writer</h4>
        </div>
        <a href="#/login" class="rounded-full h-12 w-12">
          <img
            class="w-12 h-12 rounded-full mx-auto object-cover"
            src="/src/assets/sample-img.jpg"
            alt="profile-image"
            srcset=""
          />
        </a>
      </div>
    </div>
  </header>
</template>
