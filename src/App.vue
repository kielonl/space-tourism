<template>
  <main id="main">
    <router-view v-slot="{ Component }">
      <transition name="fade" mode="out-in">
        <component :is="Component" :key="$route.path" />
      </transition>
    </router-view>
  </main>
</template>

<script setup lang="ts">
import { RouterView } from "vue-router";
import "@/assets/main.css";
</script>

<style scoped lang="scss">
#main {
  background: black;
}
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s;
}

.fade-enter,
.fade-leave-to {
  opacity: 0;
}
</style>
