<script setup></script>
<template>
 <button class="primary-button">
  <slot></slot>
 </button>
</template>
<style lang='scss' scoped>
@import '../../assets/main';
.primary-button {
  border-radius: 16px;
  background-color: transparent;
  color: $main-color-text;
  border: 1px solid $main-color-border;
  font-size: 20px;
  font-weight: 600;
  padding: 16px 32px;
  cursor: pointer;
}
</style>