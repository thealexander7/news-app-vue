<script setup>
import { ref, onMounted } from 'vue';

import { BASE_URL } from '@/constants';

import NewsItems from '@/components/NewsItems.vue';
import VButton from '@/components/UI/VButton.vue';
import VSpinner from '@/components/shared/VSpinner.vue'

const allNews = ref([])
const totalPages = ref(0)
const currentPage = ref(1)
const isLoading = ref(false)

const getAllNews = () => {
  isLoading.value = true
  fetch(`${BASE_URL}`)
    .then(response => response.json())
    .then(data => {
      allNews.value = data.items
      totalPages.value = data.nav.total
      isLoading.value = false;
    })
    .catch(err => console.error(err));
}

const fetchMore = () => {
  currentPage.value += 1
  isLoading.value = true
  fetch(`${BASE_URL}/${currentPage.value}/`)
    .then(response => response.json())
    .then(data => {
      allNews.value = data.items
      totalPages.value = data.nav.total
      isLoading.value = false
    })
    .catch(err => console.error(err));
}

onMounted(getAllNews)
</script>

<template>
  <template v-if="isLoading">
    <v-spinner></v-spinner>
  </template>
  <template v-else>
    <NewsItems class='all-news' v-if='allNews' :all-news='allNews'>
    </NewsItems>
    <v-button v-if='currentPage != totalPages' class="more-news-button" @click="fetchMore">
      Загрузить ещё
    </v-button>
  </template>
</template>

<style lang='scss' scoped>
.all-news {
  margin-top: 64px;
  margin-bottom: 72px;
}

.more-news-button {
  display: block;
  margin: 0 auto;
}
</style>