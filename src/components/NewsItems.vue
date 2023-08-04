<script setup>
import NewsItem from './NewsItem.vue';

defineProps({
  allNews: {
    type: Array,
    required: true
  }
})
</script>

<template>
  <div class="news-items">
    <NewsItem v-for='item in allNews' :key='item.code' :news-item='item'>
    </NewsItem>
  </div>
</template>

<style lang='scss' scoped>
.news-items {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  gap: 48px;

  @media screen and (max-width: 800px) {
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  }
}
</style>