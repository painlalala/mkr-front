<script setup>
import { RouterView } from 'vue-router'
import HeaderNav from './components/HeaderNav.vue'
import { isAuthenticated } from '@/stores/auth'
</script>

<template>
  <HeaderNav v-if="isAuthenticated" />
  <main class="app-main" :class="{ authed: isAuthenticated }">
    <RouterView />
  </main>
</template>

<style scoped>
:host { display:block; }
:root { --header-h: 63px }
.app-main {
  width: 100%;
  min-height: 100vh;
}
.app-main.authed {
  padding-top: var(--header-h);
}
</style>
