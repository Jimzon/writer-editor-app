
<script setup>
import { ref, computed } from 'vue'
// import Navbar from './components/Navbar.vue'
import Login from './pages/Login.vue'
import Signup from './pages/Signup.vue'
import Home from './pages/home/Home.vue'
import NavbarDashboard from './pages/dashboard/NavbarDashboard.vue'
import HomeDashboardVue from './pages/dashboard/HomeDashboard.vue'
import WriterForm from './pages/WriterForm.vue'

const routes = {
  '/': Home,
  '/login': Login,
  '/sign-up': Signup,
  '/dashboard': HomeDashboardVue,
  '/writer-form': WriterForm,
}

const currentPath = ref(window.location.hash)

window.addEventListener('hashchange', () => {
  currentPath.value = window.location.hash
})

const currentView = computed(() => {
  return routes[currentPath.value.slice(1) || '/'] || NotFound
})
</script>

<template>
    <header>
      <!-- <Navbar /> -->
      <NavbarDashboard />
    </header>

    

      <main>  
        <component :is="currentView" />
      </main>
</template>

