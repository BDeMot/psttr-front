<template>
  <div>
    <img src="~/public/img/jnews.png" alt="Nuxt Logo" class="jnews" />
    <slot />
    <Ticker />
  </div>
</template>

<script setup>
  import Ticker from '~/components/ticker.vue'  
</script>

<style lang="scss">
  .jnews {
    position: absolute;
    top: 2%;
    left: 2%;
    // transform: translate(-50%, -50%);
    width: 200px;
  }
</style>