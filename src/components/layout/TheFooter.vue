<script setup></script>
<template>
  <footer class='footer'>
    <div class='container'>
      <div class='footer__copyright'>
        <img src="@/assets/images/logo.svg" alt="">
        <div class='footer__text'>© alpha, 2023</div>
      </div>
    </div>
  </footer>
</template>
<style lang='scss' scoped>
@import '@/assets/main';
.footer {
  display: flex;
  align-items: center;
  margin-top: 79px;
  height: 200px;
  background-color: $background-badge;

  &__text {
    color: $secondary-color-text;
  }
}
</style>