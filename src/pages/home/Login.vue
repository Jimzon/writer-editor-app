<script setup></script>

<template>
  <div class="p-3 max-w-lg mx-auto">
    <h1 class="text-2xl text-center font-semibold my-7">Login</h1>
    <form class="flex flex-col gap-4">
      <input
        type="email"
        placeholder="email"
        class="border p-3 rounded-lg"
        id="email"
      />
      <input
        type="password"
        placeholder="password"
        class="border p-3 rounded-lg"
        id="password"
      />

      <button
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
