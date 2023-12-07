<script setup></script>

<template>
  <div class="py-24 justify-center mx-auto items-center max-w-4xl p-3">
    <div class="flex justify-between items-center py-6">
      <h2 class="font-semibold text-xl">Users List</h2>
      <a
        href=""
        class="bg-sky-800 flex text-white font-normal py-1.5 px-3.5 items-center text-md rounded-full"
      >
        <span class="text-md pr-2">+</span>Create User
      </a>
    </div>
    <table class="min-w-full border border-gray-300">
      <thead>
        <tr>
          <th class="py-2 px-4 border-b">Image</th>
          <th class="py-2 px-4 border-b">Name</th>
          <th class="py-2 px-4 border-b">Type</th>
          <th class="py-2 px-4 border-b">Status</th>
        </tr>
      </thead>
      <tbody class="mx-auto items-center text-center">
        <tr>
          <td class="py-2 px-4 border-b">
            <img
              src="/src/assets/cat.png"
              alt="User 1"
              class="w-14 h-10 object-cover rounded-lg mx-auto"
            />
          </td>
          <td class="py-2 px-4 border-b">John Doe</td>
          <td class="py-2 px-4 border-b">Writer</td>
          <td class="py-2 px-4 border-b">
            <span class="bg-green-500 text-white py-1.5 px-4 rounded-lg"
              >Active</span
            >
          </td>
        </tr>
        <tr>
          <td class="py-2 px-4 border-b">
            <img
              src="/src/assets/cat.png"
              alt="User 2"
              class="w-14 h-10 object-cover rounded-lg mx-auto"
            />
          </td>
          <td class="py-2 px-4 border-b">Jane Doe</td>
          <td class="py-2 px-4 border-b">Editor</td>
          <td class="py-2 px-4 border-b">
            <span class="bg-red-500 text-white py-1.5 px-4 rounded-lg"
              >Inactive</span
            >
          </td>
        </tr>
        <tr>
          <td class="py-2 px-4 border-b">
            <img
              src="/src/assets/cat.png"
              alt="User 3"
              class="w-14 h-10 object-cover rounded-lg mx-auto"
            />
          </td>
          <td class="py-2 px-4 border-b">John Doe</td>
          <td class="py-2 px-4 border-b">Writer</td>
          <td class="py-2 px-4 border-b">
            <span class="bg-green-500 text-white py-1.5 px-4 rounded-lg"
              >Active</span
            >
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>
