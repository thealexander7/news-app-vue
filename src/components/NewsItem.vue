<script setup>
import moment from "moment";

defineProps({
  newsItem: {
    type: Object,
    required: true
  }
})
</script>
<template>
  <div class="news-item">
    <img v-if='newsItem.image' class='news-item__image' :src="newsItem.image" :alt="newsItem.name">
    <div class="news-item__info">
      <div class='news-item__info-text'>
        <div class="news-item__date">
          <span class="news-item__date-day">{{ moment(newsItem.date).format('D') }}</span>
          <span class="news-item__date-month">{{ moment(newsItem.date).format('MMMM Y') }}</span>
        </div>
        <span class="news-item__title">{{ newsItem.name }}</span>
        <p class="news-item__preview-text">
          {{ newsItem.previewText }}
        </p>
      </div>
      <div class="news-item__badge">
        {{ newsItem.type.value }}
      </div>
    </div>
  </div>
</template>
<style lang='scss' scoped>
@import '@/assets/main';

.news-item {
  @include flex-col;
  border: 1px solid $main-color-border;
  border-radius: 16px;
  overflow: hidden;

  &__image {
    background-repeat: no-repeat;
    background-position: 50% 50%;
    background-size: cover;
  }

  &__title {
    color: $main-color-text;
  }

  &__info {
    height: 100%;
    @include flex-col;
    padding: 32px;
  }

  &__info-text {
    @include flex-col;
    gap: 16px;
  }

  &__badge {
    margin-top: auto;
    width: fit-content;
    padding: 4px 16px;
    border-radius: 16px;
    background-color: $background-badge;
    cursor: pointer;

    &:hover {
      box-shadow: 0px 4px 4px 0px rgba(0, 0, 0, 0.25);
    }
  }

  &__date {
    display: flex;
    align-items: center;
    gap: 4px;
    color: $secondary-color-text;
  }

  &__date-day {
    font-size: 36px;
  }

  &__date-month {
    font-size: 15px;
    width: min-content;
    line-height: 110%;
  }
}
</style>