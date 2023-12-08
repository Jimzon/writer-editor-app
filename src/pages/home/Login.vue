<script setup>
import { ref } from "vue";
import { useRouter } from "vue-router";

const apiUrl = "http://localhost:8000";
const username = ref("");
const password = ref("");

const data = ref({});
const token = ref("");
const errors = ref();
const router = useRouter();

const login = async () => {
  errors.value = null;
  const userData = {
    username: username.value,
    password: password.value,
  };
  try {
    const response = await fetch(`${apiUrl}/api/login/`, {
      method: "POST",
      headers: {
        "Content-Type": "application/json",
      },
      body: JSON.stringify(userData),
    });

    if (!response.ok) {
      errors.value = await response.json();
      throw new Error(`HTTP error! Status: ${response.status}`);
    }

    const data = await response.json();
    console.log(data);

    token.value = responseData.token;
    router.push("/company");

    return data;
  } catch (error) {
    console.log(error.response);
    console.error("Error signing up:", error);
    throw error;
  }
};
</script>

<template>
  <div class="p-3 max-w-lg mx-auto">
    <h1 class="text-2xl text-center font-semibold my-7">Login</h1>
    <form class="flex flex-col gap-4">
      <input
        v-model="username"
        type="text"
        placeholder="username"
        class="border p-3 rounded-lg"
        id="username"
      />
      <input
        v-model="password"
        type="password"
        placeholder="password"
        class="border p-3 rounded-lg"
        id="password"
      />
      <p v-if="errors" class="text-red-400">{{ errors.non_field_errors[0] }}</p>
      <!-- {{ data }} -->

      <button
        @click="login"
        class="bg-sky-700 text-white p-3 rounded-lg uppercase hover:opacity-95"
      >
        Sign in
      </button>
    </form>
    <div class="flex gap-2 mt-5">
      <p>Dont have an account?</p>
      <a href="#/sign-up">
        <span class="text-sky-700">Sign up</span>
      </a>
    </div>
  </div>
</template>
