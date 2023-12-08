<script setup>
import { ref } from "vue";
import { globalState } from "@/store";
import { useRouter } from "vue-router";

const router = useRouter();
const articles = ref([]);

const goToRoute = () => {};

const apiUrl = "http://localhost:8000";
const name = ref("");
const status = ref("");
const errors = ref();
const token = globalState.user.token;

const getArticles = async () => {
  errors.value = null;
  try {
    const response = await fetch(`${apiUrl}/api/articles/`, {
      method: "GET",
      headers: {
        "Content-Type": "application/json",
        Authorization: `Token ${token}`,
      },
    });

    if (!response.ok) {
      errors.value = await response.json();
      throw new Error(`HTTP error! Status: ${response.status}`);
    }

    articles = await response.json();
  } catch (error) {
    console.error("Error signing up:", error);
    throw error;
  }
};
</script>

<template>
  <div class="items-center max-w-4xl py-3">
    {{ articles }}
    <h2 class="font-medium py-2">For Edit</h2>

    <div
      class="flex justify-between bg-slate-100 items-center p-4 my-4 rounded-md shadow-lg"
    >
      <div class="flex gap-2 bg-red">
        <div>
          <a href="">
            <img
              class="w-18 h-16 rounded-md"
              src="/src/assets/cat.png"
              alt=""
              srcset=""
            />
          </a>
        </div>
        <div class="block">
          <h2 class="font-medium font-red">Title Sample Test</h2>
          <p class="text-[10px]">December 12, 2023</p>
          <p class="text-xs font-medium">Author: Jimzon Sample</p>
          <p class="text-xs font-medium">Editor: Sample Name</p>
        </div>
      </div>
      <div class="block text-white">
        <div>
          <a href="" class="px-8 py-1.5 rounded-lg bg-yellow-500"> For Edit </a>
        </div>
        <div class="mt-4">
          <a href="" class="text-sky-800"> View Article > </a>
        </div>
      </div>
    </div>
    <div
      class="flex justify-between bg-slate-100 items-center p-4 my-4 rounded-md shadow-lg"
    >
      <div class="flex gap-2 bg-red">
        <div>
          <a href="">
            <img
              class="w-18 h-16 rounded-md"
              src="/src/assets/cat.png"
              alt=""
              srcset=""
            />
          </a>
        </div>
        <div class="block">
          <h2 class="font-medium font-red">Title Sample Test</h2>
          <p class="text-[10px]">December 12, 2023</p>
          <p class="text-xs font-medium">Author: Jimzon Sample</p>
          <p class="text-xs font-medium">Editor: Sample Name</p>
        </div>
      </div>
      <div class="block text-white">
        <div>
          <a href="" class="px-8 py-1.5 rounded-lg bg-yellow-500"> For Edit </a>
        </div>
        <div class="mt-4">
          <a href="" class="text-sky-800"> View Article > </a>
        </div>
      </div>
    </div>
  </div>
</template>
