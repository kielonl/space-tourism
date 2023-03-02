<template>
  <div class="header-menu">
    <div class="close-container">
      <div class="close" @click="toggleMobileMenu"></div>
    </div>
    <nav>
      <RouterLink
        to="/"
        class="nav-text"
        :class="{ selected: currentRoute === 'home' }"
        ><div><span class="nav-number">00</span> HOME</div></RouterLink
      >
      <RouterLink
        to="/destination"
        class="nav-text"
        :class="{ selected: currentRoute === 'destination' }"
        ><div><span class="nav-number">01</span> DESTINATION</div></RouterLink
      >
      <RouterLink
        to="/crew"
        class="nav-text"
        :class="{ selected: currentRoute === 'crew' }"
        ><div><span class="nav-number">02</span> CREW</div></RouterLink
      >
      <RouterLink
        to="/technology"
        class="nav-text"
        :class="{ selected: currentRoute === 'technology' }"
        ><div><span class="nav-number">03</span> TECHNOLOGY</div></RouterLink
      >
    </nav>
  </div>
</template>

<script setup lang="ts">
import { computed } from "vue";
import { RouterLink, useRoute } from "vue-router";

interface Props {
  toggleMobileMenu: (payload: MouseEvent) => void;
}

defineProps<Props>();

const route = useRoute();
const currentRoute = computed(() => route.name);
</script>

<style lang="scss">
.header-menu {
  display: none;
}
@media (max-width: 375px) {
  .header-menu {
    display: block;
    position: absolute;
    top: 0;
    right: 0;
    height: 100%;
    background: rgba(255, 255, 255, 0.04);
    backdrop-filter: blur(40px);
    z-index: 2;
    .close-container {
      .close {
        position: absolute;
        top: 30px;
        right: 30px;
        width: 32px;
        height: 32px;
      }
      .close:before,
      .close:after {
        content: " ";
        position: absolute;
        left: 15px;
        height: 33px;
        width: 2px;
        background-color: #d0d6f9;
        cursor: pointer;
      }
      .close:before {
        transform: rotate(45deg);
      }
      .close:after {
        transform: rotate(-45deg);
      }
    }

    nav {
      display: flex;
      flex-direction: column;
      justify-content: center;
      margin-top: 40%;
      margin-left: 2rem;
      gap: 1rem;
      div {
        padding-right: 2rem;
      }
      .selected {
        border-right: 4px solid white;
      }
      .nav-number {
        font-weight: bold;
        margin-right: 2rem;
      }
      font-weight: 100;
    }
  }
}
</style>
