<script setup>

</script>

<template>
    <div class="py-24 justify-center mx-auto items-center max-w-4xl p-3">
        <div class="mb-4">
        <label for="title" class="block text-sm font-medium text-gray-600">Title</label>
        <input type="text" id="title" name="title" class="mt-1 p-2 border border-gray-300 rounded-md w-full">
    </div>
    <div class="mb-4">
        <label for="company" class="block text-sm font-medium text-gray-600">Related Company</label>
        <select id="company" name="company" class="mt-1 p-2 border border-gray-300 rounded-md w-full">
            <option value="company1">Company 1</option>
            <option value="company2">Company 2</option>
            <option value="company3">Company 3</option>
        </select>
    </div>
    <div class="mb-4">
        <label for="content" class="block text-sm font-medium text-gray-600">Content</label>
        <textarea id="content" name="content" rows="4" class="mt-1 p-2 border border-gray-300 rounded-md w-full"></textarea>
    </div>
    <div class="mb-4">
        <label for="image" class="block text-sm font-medium text-gray-600">Upload Image</label>
        <input type="file" id="image" name="image" class="mt-1 p-2 border border-gray-300 rounded-md w-full">
    </div>
    <div class="flex justify-end gap-2 ">
        <button type="button" class="px-4 py-2 bg-green-500 text-white rounded-md hover:bg-green-600 focus:outline-none focus:shadow-outline-blue active:bg-blue-800">
            Save
        </button>
        <button type="button" class="px-4 py-2 bg-blue-500 text-white rounded-md hover:bg-blue-600 focus:outline-none focus:shadow-outline-blue active:bg-blue-800">
            Publish
        </button>
    </div>
    </div>

</template>
