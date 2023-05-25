<script setup>
  import LoadingUrl from '../assets/images/loading.png'
</script>

<template>
  <img 
    class="loading"
    :src="LoadingUrl" 
    width="100"
    height="100"
  >
</template>

<style scoped>
  .loading {
    animation: rotate 4s linear infinite;
  }

  .loading + .loading {
    margin-left: 50px;
  }

  @keyframes rotate {
    0% {
      transform: rotate(0deg)
    }
    40% {
      transform: rotate(90deg)
    }
    60% {
      transform: rotate(270deg)
    }
    100% {
      transform: rotate(360deg)
    }
  }
</style>