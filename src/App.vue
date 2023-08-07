<script setup>
import VFooter from '@/components/layout/TheFooter.vue';
import VHeader from '@/components/layout/TheHeader.vue';

import SubHeader from '@/components/SubHeader.vue';
</script>

<template>
  <v-header />
  <sub-header></sub-header>
  <main class='container'>
    <RouterView />
  </main>
  <v-footer />
</template>

<style scoped></style>
