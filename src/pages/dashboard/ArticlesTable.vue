<script setup></script>

<template>
  <div class="justify-center mx-auto items-center max-w-4xl p-3">
    <h2 class="font-medium py-2">Articles</h2>
    <div
      class="flex justify-between bg-slate-100 items-center p-4 my-4 rounded-md shadow-lg"
    >
      <table class="min-w-full">
        <thead>
          <tr>
            <th class="py-2 px-4 border-b">Image</th>
            <th class="py-2 px-4 border-b">Title</th>
            <th class="py-2 px-4 border-b">Writer</th>
            <th class="py-2 px-4 border-b">Editor</th>
            <th class="py-2 px-4 border-b">Status</th>
          </tr>
        </thead>
        <tbody class="mx-auto items-center text-center">
          <!-- Sample Row 1 -->
          <tr>
            <td class="py-2 px-4 border-b">
              <img
                src="/src/assets/cat.png"
                alt="Image 1"
                class="w-14 h-10 object-cover rounded-lg mx-auto"
              />
            </td>
            <td class="py-2 px-4 border-b">Title 1</td>
            <td class="py-2 px-4 border-b">Writer 1</td>
            <td class="py-2 px-4 border-b">Editor 1</td>
            <td class="py-2 px-4 border-b">
              <span class="bg-green-500 text-white py-1.5 px-4 rounded-lg"
                >Published</span
              >
            </td>
          </tr>

          <!-- Sample Row 2 -->
          <tr class="">
            <td class="py-2 px-4 border-b">
              <img
                src="/src/assets/cat.png"
                alt="Image 2"
                class="w-14 h-10 object-cover rounded-lg mx-auto"
              />
            </td>
            <td class="py-2 px-4 border-b">Title 2</td>
            <td class="py-2 px-4 border-b">Writer 2</td>
            <td class="py-2 px-4 border-b">Editor 2</td>
            <td class="py-2 px-4 border-b">
              <span class="bg-yellow-500 text-white py-1.5 px-4 rounded-lg"
                >For Edit</span
              >
            </td>
          </tr>

          <!-- Sample Row 3 -->
          <tr class="">
            <td class="py-2 px-4 border-b">
              <img
                src="/src/assets/cat.png"
                alt="Image 3"
                class="w-14 h-10 object-cover rounded-lg mx-auto"
              />
            </td>
            <td class="py-2 px-4 border-b">Title 3</td>
            <td class="py-2 px-4 border-b">Writer 3</td>
            <td class="py-2 px-4 border-b">Editor 3</td>
            <td class="py-2 px-4 border-b">
              <span class="bg-green-500 text-white py-1.5 px-4 rounded-lg"
                >Published</span
              >
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>
