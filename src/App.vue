
<script setup>
import { ref, computed } from 'vue'
import Navbar from './components/Navbar.vue'
import Login from './pages/Login.vue'
import Home from './pages/home/Home.vue'

const routes = {
  '/': Home,
  '/login': Login
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
      <Navbar />
    </header>

      <main>  
        <component :is="currentView" />
      </main>
</template>

