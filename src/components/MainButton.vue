<template>
  <button><h4>EXPLORE</h4></button>
</template>

<script setup lang="ts"></script>

<style scoped lang="scss">
button {
  background: #ffffff;
  border-radius: 50%;
  height: 20rem;
  width: 20rem;
  outline: none;
  border: none;
  cursor: pointer;
  transition: all 300ms;
  &:hover {
    outline: 5rem solid rgba(255, 255, 255, 10.36%);
  }
  h4 {
    color: #0b0d17;
  }
}
</style>
