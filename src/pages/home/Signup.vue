<script setup>
import { ref } from "vue";
import { useRouter } from "vue-router";

const apiUrl = "http://localhost:8000";
const username = ref("");
const email = ref("");
const name = ref("");
const password = ref("");
const router = useRouter();

const signup = async () => {
  const userData = {
    username: username.value,
    email: email.value,
    name: name.value,
    password: password.value,
  };
  try {
    const response = await fetch(`${apiUrl}/api/signup/`, {
      method: "POST",
      headers: {
        "Content-Type": "application/json",
      },
      body: JSON.stringify(userData),
    });

    if (!response.ok) {
      throw new Error(`HTTP error! Status: ${response.status}`);
    }

    const data = await response.json();
    router.push("/login");

    return data;
  } catch (error) {
    console.error("Error signing up:", error);
    throw error;
  }
};
</script>

<template>
  <div class="p-3 max-w-lg mx-auto">
    <h1 class="text-2xl text-center font-semibold my-7">Sign up</h1>
    <form class="flex flex-col gap-4">
      <input
        v-model="name"
        type="text"
        placeholder="Full Name"
        class="border p-3 rounded-lg"
        id="name"
      />
      <input
        v-model="username"
        type="text"
        placeholder="Username"
        class="border p-3 rounded-lg"
        id="name"
      />
      <input
        v-model="email"
        type="email"
        placeholder="Email"
        class="border p-3 rounded-lg"
        id="email"
      />
      <input
        v-model="password"
        type="password"
        placeholder="Password"
        class="border p-3 rounded-lg"
        id="password"
      />

      <!-- <select
        id="company"
        name="company"
        class="mt-1 p-2 border border-gray-300 rounded-md w-full"
      >
        <option value="company1">Writer</option>
        <option value="company2">Editor</option>
      </select> -->
      <button
        @click="signup"
        class="bg-sky-700 text-white p-3 rounded-lg uppercase hover:opacity-95"
      >
        Sign up
      </button>
    </form>
    <div class="flex gap-2 mt-5">
      <p>Have an account?</p>
      <a href="#/login">
        <span className="text-sky-700">Log in</span>
      </a>
    </div>
  </div>
</template>
