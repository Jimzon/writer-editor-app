<script setup>
import { ref } from "vue";

const apiUrl = "http://localhost:8000";

const name = ref("");
const status = ref("");

const saveCompany = async () => {
  const userData = {
    name: name.value,
    statuts: status.value,
  };
  try {
    const response = await fetch(`${apiUrl}/api/companies/`, {
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

    return data;
  } catch (error) {
    console.error("Error signing up:", error);
    throw error;
  }
};
</script>

<template>
  <div class="py-24 justify-center mx-auto items-center max-w-4xl p-3">
    <form @submit.prevent="submitForm" class="grid grid-cols-2 gap-4">
      <div>
        <div class="mb-4">
          <label
            for="companyName"
            class="block text-sm font-medium text-gray-600"
            >Company Name</label
          >
          <input
            v-model="name"
            type="text"
            id="companyName"
            name="companyName"
            class="mt-1 p-2 border border-gray-300 rounded-md w-full"
          />
        </div>
      </div>
      <div>
        <div class="mb-4">
          <label for="status" class="block text-sm font-medium text-gray-600"
            >Status</label
          >
          <select
            v-model="status"
            id="status"
            name="status"
            class="mt-1 p-2 border border-gray-300 rounded-md w-full"
          >
            <option value="active">Active</option>
            <option value="inactive">Inactive</option>
          </select>
        </div>
      </div>
      <div class="col-span-2">
        <label
          for="companyImage"
          class="block text-sm font-medium text-gray-600"
          >Upload Company Image</label
        >
        <input
          type="file"
          id="companyImage"
          name="companyImage"
          class="mt-1 p-2 border border-gray-300 rounded-md w-full"
          @change="handleImageUpload"
        />
      </div>
      <div class="col-span-2 mb-4">
        <label class="block text-sm font-medium text-gray-600"
          >Uploaded Image</label
        >
        <div class="w-full h-32 bg-gray-200 flex items-center justify-center">
          <img
            v-if="imageUrl"
            :src="imageUrl"
            alt="Company Image"
            class="w-full h-full object-cover"
          />
          <span v-else class="text-gray-500">Image Preview</span>
        </div>
      </div>

      <div class="col-span-2 flex justify-end">
        <button
          @click="saveCompany"
          type="submit"
          class="px-4 py-2 bg-blue-500 text-white rounded-md hover:bg-blue-600 focus:outline-none focus:shadow-outline-blue active:bg-blue-800"
        >
          Save
        </button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      companyName: "",
      status: "active",
      imageUrl: null,
    };
  },
  methods: {
    handleImageUpload(event) {
      const file = event.target.files[0];
      if (file) {
        const reader = new FileReader();
        reader.onload = (e) => {
          this.imageUrl = e.target.result;
        };
        reader.readAsDataURL(file);
      }
    },
    submitForm() {
      console.log("Form submitted:", {
        companyName: this.companyName,
        status: this.status,
        imageUrl: this.imageUrl,
      });
    },
  },
};
</script>
