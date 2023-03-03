<template>
  <main id="home">
    <HeaderMenu />
    <div class="desktop-body-wrapper">
      <div class="desktop-body--heading">
        <h5>SO, YOU WANT TO TRAVEL TO</h5>
        <h1>SPACE</h1>
        <div class="body-text">
          Let’s face it; if you want to go to space, you might as well genuinely
          go to outer space and not hover kind of on the edge of it. Well sit
          back, and relax because we’ll give you a truly out of this world
          experience!
        </div>
      </div>
      <div class="desktop-body-button-wrapper">
        <MainButton />
      </div>
    </div>
  </main>
</template>

<script setup lang="ts">
import MainButton from "@/components/MainButton.vue";
import HeaderMenu from "@/components/HeaderMenu.vue";
</script>

<style scoped lang="scss">
#home {
  background: url("https://diedieve.sirv.com/Images/background-home-desktop.jpg")
    no-repeat center center fixed;
  background-size: cover;
  height: 100vh;
  overflow: hidden;

  .desktop-body-wrapper {
    display: flex;
    .desktop-body--heading {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      width: 100%;

      h1 {
        margin: 0;
        padding: 0;
      }
      .sub-heading1 {
        color: #d0d6f9;
      }
      .body-text {
        max-width: 40rem;
      }
    }
    .desktop-body-button-wrapper {
      width: 100%;
      display: flex;
      justify-content: center;
      align-items: center;
    }
  }
}

@media (max-width: 768px) {
  #home {
    background: url("https://diedieve.sirv.com/Images/background-home-tablet.jpg")
      no-repeat center center fixed;

    .desktop-body-wrapper {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      padding: 0;
      text-align: center;
      h1 {
        font-size: 150px;
      }
      .body-text {
        padding: 0 4rem;
      }
    }
  }
}

@media (max-width: 375px) {
  #home {
    background: url("https://diedieve.sirv.com/Images/background-home-mobile.jpg")
      no-repeat center center fixed;
    .desktop-body-wrapper {
      .body-text {
        padding: 0 2rem;
      }
      h1 {
        font-size: 100px;
      }
    }
  }
}
</style>
