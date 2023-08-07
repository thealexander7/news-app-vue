<script setup></script>
<template>
  <div class='subheader'>
    <div class='container'>
      <h1 class='subheader__title'>Новости</h1>
    </div>
  </div>
</template>
<style lang='scss' scoped>
.subheader {
  height: 320px;
  background: url('@/assets/images/main-bg.png');
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;

  .container {
    display: flex;
    align-items: flex-end;
    height: 100%;
  }
}
</style>