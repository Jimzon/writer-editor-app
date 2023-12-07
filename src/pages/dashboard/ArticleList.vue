<script setup>
import ForEditList from './ForEditList.vue'
</script>

<template>
    <div class="py-24 justify-center mx-auto items-center max-w-4xl p-3">
        <div class="flex justify-between items-center">
          <h2 class="font-semibold text-xl">Articles List</h2>
            <button class="bg-sky-800 flex text-white font-normal py-2 px-4 items-center text-md rounded-full">
        <span class="text-xl pr-2">+</span>  Create Article
            </button>
        </div>
        <ForEditList />
    </div>

</template>
