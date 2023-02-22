<template>
  <div class="desktop-header--menu">
    <img src="../assets/shared/logo.svg" alt="logo" />
    <span class="desktop-header--spacer"></span>
    <nav>
      <a href="#" class="nav-text selected"
        ><span class="nav-number">00</span> Home</a
      >
      <a href="#" class="nav-text"
        ><span class="nav-number">01</span> DESTINATION</a
      >
      <a href="#" class="nav-text"><span class="nav-number">02</span> CREW</a>
      <a href="#" class="nav-text"
        ><span class="nav-number">03</span> TECHNOLOGY</a
      >
    </nav>
    <img
      src="../assets/shared/icon-hamburger.svg"
      alt="hamburger-menu"
      class="hamburger-menu"
    />
  </div>
</template>

<script setup lang="ts"></script>

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
