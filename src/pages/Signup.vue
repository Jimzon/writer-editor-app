<script setup>
</script>

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
        <input
          type="password"
          placeholder="confirm password"
          className="border p-3 rounded-lg"
          id="password"
        />

        <button className="bg-media_primary text-main_white p-3 rounded-lg uppercase hover:opacity-95">
          Sign up
        </button>
      </form>
      <div className="flex gap-2 mt-5">
        <p>Have an account?</p>
        <a href="#/login">
          <span className="text-media_primary">Log in</span>
        </a>
      </div>
    </div>
      
</template>