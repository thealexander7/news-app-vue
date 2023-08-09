<script setup>
import TheFooter from '@/components/layout/TheFooter.vue';
import TheHeader from '@/components/layout/TheHeader.vue';

import SubHeader from '@/components/SubHeader.vue';
</script>

<template>
  <TheHeader />
  <sub-header></sub-header>
  <main class="container">
    <RouterView />
  </main>
  <TheFooter />
</template>

<style scoped></style>
