<script setup>
import ForEditList from "./ForEditList.vue";
import PublishedList from "./PublishedList.vue";
</script>

<template>
  <div class="py-24 justify-center mx-auto items-center max-w-4xl p-3">
    <div class="flex justify-between items-center">
      <h2 class="font-semibold text-xl">Articles List</h2>
      <a
        href="#/writer-form"
        class="bg-sky-800 flex text-white font-normal py-1.5 px-3.5 items-center text-md rounded-full"
      >
        <span class="text-md pr-2">+</span>Create Article
      </a>
    </div>
    <ForEditList />
    <PublishedList />
  </div>
</template>
