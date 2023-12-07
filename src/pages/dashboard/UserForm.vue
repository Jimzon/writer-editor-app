<script setup></script>

<template>
  <div class="py-24 justify-center mx-auto items-center max-w-4xl p-3">
    <form action="#" method="POST" class="grid grid-cols-2 gap-4">
      <!-- Column 1 -->
      <div>
        <!-- Name Input -->
        <div class="mb-4">
          <label for="name" class="block text-sm font-medium text-gray-600"
            >Name</label
          >
          <input
            type="text"
            id="name"
            name="name"
            class="mt-1 p-2 border border-gray-300 rounded-md w-full"
          />
        </div>

        <!-- Type Dropdown -->
        <div class="mb-4">
          <label for="type" class="block text-sm font-medium text-gray-600"
            >Type</label
          >
          <select
            id="type"
            name="type"
            class="mt-1 p-2 border border-gray-300 rounded-md w-full"
          >
            <option value="writer">Writer</option>
            <option value="editor">Editor</option>
          </select>
        </div>
      </div>

      <!-- Column 2 -->
      <div>
        <!-- Lastname Input -->
        <div class="mb-4">
          <label for="lastname" class="block text-sm font-medium text-gray-600"
            >Lastname</label
          >
          <input
            type="text"
            id="lastname"
            name="lastname"
            class="mt-1 p-2 border border-gray-300 rounded-md w-full"
          />
        </div>

        <!-- Status Dropdown -->
        <div class="mb-4">
          <label for="status" class="block text-sm font-medium text-gray-600"
            >Status</label
          >
          <select
            id="status"
            name="status"
            class="mt-1 p-2 border border-gray-300 rounded-md w-full"
          >
            <option value="active">Active</option>
            <option value="inactive">Inactive</option>
          </select>
        </div>
      </div>

      <!-- Image Upload -->
      <div class="col-span-2">
        <label for="image" class="block text-sm font-medium text-gray-600"
          >Upload Image</label
        >
        <input
          type="file"
          id="image"
          name="image"
          class="mt-1 p-2 border border-gray-300 rounded-md w-full"
        />
      </div>

      <!-- Display Uploaded Image -->
      <div class="col-span-2 mb-4">
        <!-- You can use this space to display the uploaded image -->
        <!-- For demonstration, we are just using a placeholder div -->
        <div class="w-full h-32 bg-gray-200 flex items-center justify-center">
          <!-- Display uploaded image here -->
          <span class="text-gray-500">Image Preview</span>
        </div>
      </div>

      <!-- Save Button -->
      <div class="col-span-2 flex justify-end">
        <button
          type="submit"
          class="px-4 py-2 bg-blue-500 text-white rounded-md hover:bg-blue-600 focus:outline-none focus:shadow-outline-blue active:bg-blue-800"
        >
          Save
        </button>
      </div>
    </form>
  </div>
</template>
