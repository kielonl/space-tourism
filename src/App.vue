<template>
  <main id="main">
    <HeaderMenu />
    <RouterView />
  </main>
</template>

<script setup lang="ts">
import HeaderMenu from "@/components/HeaderMenu.vue";
import { RouterView } from "vue-router";
import "@/assets/main.css";
</script>

<style scoped lang="scss">
main {
  background: url("./assets/home/background-home-desktop.jpg") no-repeat center
    center fixed;
  background-size: cover;
  height: 100vh;
  overflow: hidden;
}

@media (max-width: 768px) {
  main {
    background: url("./assets/home/background-home-tablet.jpg") no-repeat center
      center fixed;
  }
}

@media (max-width: 375px) {
  main {
    background: url("./assets/home/background-home-mobile.jpg") no-repeat center
      center fixed;
  }
}
</style>
