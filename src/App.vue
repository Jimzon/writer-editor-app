<script setup>
import { ref, computed } from "vue";
import Navbar from "./components/Navbar.vue";
import Login from "./pages/home/Login.vue";
import Signup from "./pages/home/Signup.vue";
import Home from "./pages/home/Home.vue";
import NavbarDashboard from "./pages/dashboard/NavbarDashboard.vue";
import HomeDashboardVue from "./pages/dashboard/HomeDashboard.vue";
import WriterForm from "./pages/dashboard/WriterForm.vue";
import UsersList from "./pages/dashboard/UsersList.vue";
import ArticlesTable from "./pages/dashboard/ArticlesTable.vue";
import UserForm from "./pages/dashboard/UserForm.vue";
import CompanyList from "./pages/dashboard/CompanyList.vue";
import CompanyForm from "./pages/dashboard/CompanyForm.vue";

const routes = {
  "/": Home,
  "/login": Login,
  "/sign-up": Signup,
  "/dashboard": HomeDashboardVue,
  "/writer-form": WriterForm,
  "/articles-table": ArticlesTable,
  "/users-list": UsersList,
  "/user-form": UserForm,
  "/company-list": CompanyList,
  "/company-form": CompanyForm,
};

const currentPath = ref(window.location.hash);

window.addEventListener("hashchange", () => {
  currentPath.value = window.location.hash;
});

const currentView = computed(() => {
  return routes[currentPath.value.slice(1) || "/"] || NotFound;
});

const isDashboard = computed(() => {
  console.log(currentPath.value);
  return (
    currentPath.value !== "" &&
    currentPath.value !== "/" &&
    currentPath.value !== "#/" &&
    currentPath.value !== "#/login" &&
    currentPath.value !== "#/sign-up"
  );
});
</script>

<template>
  <header>
    <NavbarDashboard v-if="isDashboard" />
    <Navbar v-if="!isDashboard" />
  </header>
  <main>
    <component :is="currentView" />
  </main>
</template>
