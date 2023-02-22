<template>
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
</template>

<script setup lang="ts">
import MainButton from "@/components/MainButton.vue";
</script>

<style scoped lang="scss">
.desktop-body-wrapper {
  display: grid;
  grid-template-columns: 0.5fr 1fr;
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

@media (max-width: 768px) {
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
</style>
