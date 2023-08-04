<script setup></script>
<template>
  <div class="spinner">
    <span class="spinner-inner-1"></span>
    <span class="spinner-inner-2"></span>
    <span class="spinner-inner-3"></span>
  </div>
</template>

<style lang='scss' scoped>
@import '../../assets/main';

html { background-color: #fff; }

.spinner {
  position: absolute;
  top: calc(50% - $size / 2);
  left: calc(50% - $size / 2);
  width: $size;
  height: $size;
  animation: spinner 0.75s linear infinite;

  span {
    position: absolute;
    width: 100%;
    height: 100%;
    border-radius: 50%;
  }
  
  .spinner-inner-1 {
    background: linear-gradient(to right, rgba($secondary-color-text,0) 0%,rgba($secondary-color-text,0) 50%,$secondary-color-text 51%);
  }
  
  .spinner-inner-2 {
    background: linear-gradient(to top, rgba(#fff,0) 0%,#fff 100%);
  }
  
  .spinner-inner-3 {
    $offset: $size * 0.1;
    top: $offset;
    left: $offset;
    width: $size - ($offset * 2);
    height: $size - ($offset * 2);
    background: #fff;
  }
}

@keyframes spinner {
  0% { transform: rotate(0deg); }
  100% { transform: rotate(360deg); }
}
</style>