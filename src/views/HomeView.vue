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
        <img
          src="../assets/shared/icon-hamburger.svg"
          alt="hamburger-menu"
          class="hamburger-menu"
        />
      </div>
      <div class="desktop-body-wrapper">
        <div class="desktop-body--heading">
          <h5>SO, YOU WANT TO TRAVEL TO</h5>
          <h1>SPACE</h1>
          <div class="body-text">
            Let’s face it; if you want to go to space, you might as well
            genuinely go to outer space and not hover kind of on the edge of it.
            Well sit back, and relax because we’ll give you a truly out of this
            world experience!
          </div>
        </div>
        <div class="desktop-body-button-wrapper">
          <MainButton />
        </div>
      </div>
    </div>
  </main>
</template>

<script setup lang="ts">
import MainButton from "@/components/MainButton.vue";
</script>

<style scoped lang="scss">
main {
  background: url("../assets/home/background-home-desktop.jpg") no-repeat center
    center fixed;
  background-size: cover;
  height: 100vh;
  overflow: hidden;
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
  .desktop-body-wrapper {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    grid-template-rows: 1fr;
    grid-column-gap: 0px;
    grid-row-gap: 0px;
    padding: 6rem;
    .desktop-body--heading {
      grid-area: 1 / 1 / 2 / 2;
      display: flex;
      flex-direction: column;
      max-width: 40rem;
      h1 {
        margin: 0;
        padding: 0;
      }
      .sub-heading1 {
        color: #d0d6f9;
      }
    }
    .desktop-body-button-wrapper {
      grid-area: 1 / 2 / 2 / 3;
      button {
        position: relative;
        left: 50%;
        top: 40%;
      }
    }
  }
}

@media (max-width: 768px) {
  main {
    background: url("../assets/home/background-home-tablet.jpg") no-repeat
      center center fixed;
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
    .desktop-body-wrapper {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      padding: 0;
      text-align: center;

      .desktop-body-button-wrapper {
        button {
          left: 0;
          top: 0;
        }
      }
    }
  }
}

@media (max-width: 375px) {
  main {
    background: url("../assets/home/background-home-mobile.jpg") no-repeat
      center center fixed;

    .desktop-header--menu {
      nav {
        display: none;
      }
      .hamburger-menu {
        display: block;
      }
    }
  }
}
</style>
