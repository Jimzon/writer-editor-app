<script setup></script>

<template>
  <div class="py-24 justify-center mx-auto items-center max-w-4xl p-3">
    <div class="flex justify-between items-center py-6">
      <h2 class="font-semibold text-xl">CompanyList</h2>
      <a
        href="#/company-form"
        class="bg-sky-800 flex text-white font-normal py-1.5 px-3.5 items-center text-md rounded-full"
      >
        <span class="text-md pr-2">+</span>Add Company
      </a>
    </div>
    <table id="companyTable" class="min-w-full border border-gray-300">
      <thead>
        <tr>
          <th class="py-2 px-4 border-b">Logo</th>
          <th class="py-2 px-4 border-b">Company Name</th>
          <th class="py-2 px-4 border-b">Status</th>
        </tr>
      </thead>
      <tbody class="mx-auto text-center">
        <tr>
          <td class="py-2 px-4 border-b logo-cell">
            <input
              type="file"
              id="logo1"
              name="logo1"
              class="hidden"
              onchange="displayLogo('logo1', 'logoImage1')"
            />
            <label for="logo1" class="cursor-pointer">
              <img
                id="logoImage1"
                src="https://picsum.photos/id/1015/100/100"
                alt="Company Logo"
                class="w-10 h-10 object-cover rounded-lg mx-auto"
              />
            </label>
          </td>
          <td class="py-2 px-4 border-b">Company ABC</td>
          <td class="py-2 px-4 border-b">
            <span class="bg-green-500 text-white py-1.5 px-4 rounded-lg"
              >Active</span
            >
          </td>
        </tr>

        <!-- Sample Row 2 -->
        <tr>
          <td class="py-2 px-4 border-b logo-cell">
            <input
              type="file"
              id="logo2"
              name="logo2"
              class="hidden"
              onchange="displayLogo('logo2', 'logoImage2')"
            />
            <label for="logo2" class="cursor-pointer">
              <img
                id="logoImage2"
                src="https://picsum.photos/id/1021/100/100"
                alt="Company Logo"
                class="w-10 h-10 object-cover rounded-lg mx-auto"
              />
            </label>
          </td>
          <td class="py-2 px-4 border-b">Company XYZ</td>
          <td class="py-2 px-4 border-b">
            <span class="bg-red-500 text-white py-1.5 px-4 rounded-lg"
              >Inactive</span
            >
          </td>
        </tr>
        <!-- Add more rows as needed -->
      </tbody>
    </table>
  </div>
</template>
