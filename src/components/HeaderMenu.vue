<template>
  <div class="desktop-header--menu">
    <MobileHeaderMenu
      v-if="showMobileMenu"
      :toggleMobileMenu="toggleMobileMenu"
    />

    <img src="../assets/shared/logo.svg" alt="logo" />
    <span class="desktop-header--spacer"></span>
    <nav>
      <RouterLink
        to="/"
        class="nav-text"
        :class="{ selected: currentRoute === 'home' }"
        ><span class="nav-number">00</span> Home</RouterLink
      >
      <RouterLink
        to="/destination"
        class="nav-text"
        :class="{ selected: currentRoute === 'destination' }"
        ><span class="nav-number">01</span> DESTINATION</RouterLink
      >
      <RouterLink
        to="/crew"
        class="nav-text"
        :class="{ selected: currentRoute === 'crew' }"
        ><span class="nav-number">02</span> CREW</RouterLink
      >
      <RouterLink
        to="/technology"
        class="nav-text"
        :class="{ selected: currentRoute === 'technology' }"
        ><span class="nav-number">03</span> TECHNOLOGY</RouterLink
      >
    </nav>
    <img
      src="../assets/shared/icon-hamburger.svg"
      alt="hamburger-menu"
      class="hamburger-menu"
      @click="toggleMobileMenu"
    />
  </div>
</template>

<script setup lang="ts">
import MobileHeaderMenu from "@/components/MobileHeaderMenu.vue";

import { computed, ref } from "vue";
import { useRoute } from "vue-router";
import { RouterLink } from "vue-router";

const route = useRoute();
const currentRoute = computed(() => route.name);
const showMobileMenu = ref(false);

const toggleMobileMenu = () => {
  showMobileMenu.value = !showMobileMenu.value;
};
</script>

<style scoped lang="scss">
.desktop-header--menu {
  display: flex;
  align-items: center;
  margin: 2rem 0rem 2rem 2rem;
  .hamburger-menu {
    display: none;
    cursor: pointer;
  }

  .desktop-header--spacer {
    flex: 1;
    border-bottom: 1px solid #ffffff;
    transform: translateX(4%);
    z-index: 2;
    opacity: 0.25;
  }

  nav {
    z-index: 1;
    display: flex;
    gap: 2rem;
    background: rgba(255, 255, 255, 0.04);
    backdrop-filter: blur(20px);
    padding: 2rem 8rem 2rem 8rem;
    .nav-number {
      font-weight: bold;
    }
    .nav-text.selected::after,
    .nav-text:not(.selected):hover::after {
      content: "";
      display: block;
      position: relative;
      background-color: white;
      height: 4px;
      width: 100%;
      top: 100%;
      margin: 0;
      padding: 0;
    }
    .nav-text:not(.selected):hover::after {
      background-color: gray;
    }
  }
}

@media (max-width: 765px) {
  .desktop-header--menu {
    margin: 0;
    img {
      margin: 1rem;
    }
    .desktop-header--spacer {
      border: unset;
    }
    nav {
      padding: 2rem;
      gap: 2rem;
      .nav-number {
        display: none;
      }
    }
  }
}

@media (max-width: 375px) {
  .desktop-header--menu {
    nav {
      display: none;
    }
    .hamburger-menu {
      display: block;
    }
  }
}
</style>
