<script setup></script>

<template>
  <div className="p-3 max-w-lg mx-auto">
    <h1 className="text-2xl text-center font-semibold my-7">Sign up</h1>
    <form className="flex flex-col gap-4">
      <input
        type="email"
        placeholder="email"
        className="border p-3 rounded-lg"
        id="email"
      />
      <input
        type="password"
        placeholder="password"
        className="border p-3 rounded-lg"
        id="password"
      />

      <select
        id="company"
        name="company"
        class="mt-1 p-2 border border-gray-300 rounded-md w-full"
      >
        <option value="company1">Writer</option>
        <option value="company2">Editor</option>
      </select>
      <button
        className="bg-sky-700 text-white p-3 rounded-lg uppercase hover:opacity-95"
      >
        Sign up
      </button>
    </form>
    <div className="flex gap-2 mt-5">
      <p>Have an account?</p>
      <a href="#/login">
        <span className="text-sky-700">Log in</span>
      </a>
    </div>
  </div>
</template>
