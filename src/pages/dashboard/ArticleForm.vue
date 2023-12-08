<script setup>
import { ref, onMounted, reactive } from "vue";
import { globalState } from "@/store";

const errors = ref(null);
const selectedCompanyId = ref(null);
const companies = ref([]);
const token = globalState.user.token;
const apiUrl = "http://localhost:8000";

const fetchData = async () => {
  try {
    const response = await fetch(`${apiUrl}/api/companies`, {
      headers: {
        Authorization: `Token ${token}`,
      },
    });
    if (!response.ok) {
      throw new Error(`HTTP error! Status: ${response.status}`);
    }
    const data = await response.json();
    companies.value = data;

    console.log(data);
  } catch (error) {
    console.error("Error fetching data:", error);
  }
};

const getSelectedCompanyName = (companyId) => {
  const selectedCompany = companies.value.find(
    (company) => company.id === companyId
  );
  return selectedCompany ? selectedCompany.name : "";
};

onMounted(() => {
  fetchData();
});
const articleData = reactive({
  title: "",
  body: "",
  company: "",
});
const storeArticle = async () => {
  errors.value = null;

  try {
    const response = await fetch(`${apiUrl}/api/articles/`, {
      method: "POST",
      headers: {
        "Content-Type": "application/json",
        Authorization: `Token ${token}`,
      },
      body: JSON.stringify(articleData),
    });

    if (!response.ok) {
      errors.value = await response.json();
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
  <div class="py-8 md:py-24 justify-center mx-auto items-center max-w-4xl p-3">
    <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
      <div>
        <div class="mb-4">
          <label for="title" class="block text-sm font-medium text-gray-600"
            >Title</label
          >
          <input
            v-model="articleData.title"
            type="text"
            id="title"
            name="title"
            class="mt-1 p-2 border border-gray-300 rounded-md w-full"
          />
        </div>
      </div>

      <div>
        <div class="mb-4">
          <label for="company" class="block text-sm font-medium text-gray-600"
            >Related Company</label
          >

          <select
            v-model="articleData.company"
            id="company"
            name="company"
            class="mt-1 p-2 border border-gray-300 rounded-md w-full"
          >
            <option
              v-for="company in companies"
              :key="company.id"
              :value="company.id"
            >
              {{ company.name }}
            </option>
          </select>
        </div>
      </div>
    </div>

    <div class="mb-4">
      <label for="content" class="block text-sm font-medium text-gray-600"
        >Content</label
      >
      <textarea
        v-model="articleData.body"
        id="content"
        name="content"
        rows="4"
        class="mt-1 p-2 border border-gray-300 rounded-md w-full"
      ></textarea>
    </div>
    <div class="mb-4">
      <label for="image" class="block text-sm font-medium text-gray-600"
        >Upload Image</label
      >
      <input
        type="file"
        id="image"
        name="image"
        class="mt-1 p-2 border border-gray-300 rounded-md w-full"
        @change="handleFileChange"
      />
    </div>

    <!-- Action Buttons -->
    <div class="flex justify-end gap-2 mt-4">
      <button
        @click="storeArticle"
        type="button"
        class="px-4 py-2 bg-green-500 text-white rounded-md hover:bg-green-600 focus:outline-none focus:shadow-outline-blue active:bg-blue-800"
      >
        Save
      </button>
      <button
        type="button"
        class="px-4 py-2 bg-blue-500 text-white rounded-md hover:bg-blue-600 focus:outline-none focus:shadow-outline-blue active:bg-blue-800"
      >
        Publish
      </button>
    </div>
  </div>
</template>
