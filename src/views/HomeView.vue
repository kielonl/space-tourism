<template>
  <main id="home">
    <div class="desktop-header">
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
          <a href="#" class="nav-text"
            ><span class="nav-number">02</span> CREW</a
          >
          <a href="#" class="nav-text"
            ><span class="nav-number">03</span> TECHNOLOGY</a
          >
        </nav>
      </div>
    </div>
  </main>
</template>

<script setup lang="ts"></script>

<style scoped lang="scss">
main {
  background-image: url("../assets/home/background-home-desktop.jpg");
  background-size: cover;
  height: 100vh;
  overflow: hidden;
  .desktop-header--menu {
    display: flex;
    align-items: center;
    margin: 2rem 0rem 2rem 2rem;

    .desktop-header--spacer {
      flex: 1;
      border-bottom: 1px solid #ffffff;
      transform: translateX(4%);
      z-index: 2;
    }

    nav {
      z-index: 1;
      display: flex;
      gap: 5rem;
      background: rgba(255, 255, 255, 0.04);
      backdrop-filter: blur(20px);
      padding: 2rem 8rem 2rem 8rem;
      .nav-number {
        font-weight: bold;
      }
      .nav-text.selected::after {
        content: "";
        display: block;
        position: relative;
        background: white;
        height: 4px;
        width: 100%;
        top: 100%;
        margin: 0;
        padding: 0;
      }
    }
  }
}
</style>
