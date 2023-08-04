<script setup>
import VFooter from '@/components/layout/VFooter.vue';
import VHeader from '@/components/layout/VHeader.vue';
import VSubheader from '@/components/layout/VSubHeader.vue';
</script>

<template>
  <v-header></v-header>
  <v-subheader></v-subheader>
  <main class='container'>
    <RouterView />
  </main>
  <v-footer></v-footer>
</template>

<style scoped></style>
