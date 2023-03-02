<template>
  <button><h4>EXPLORE</h4></button>
</template>

<script setup lang="ts"></script>

<style scoped lang="scss">
button {
  background: #ffffff;
  border-radius: 50%;
  padding: 5rem 5rem;
  font-size: calc(1rem + 1vw);
  outline: none;
  border: none;
  cursor: pointer;
  transition: outline 300ms;
  &:hover {
    outline: 3vmax solid rgba(255, 255, 255, 10.36%);
  }
  h4 {
    color: #0b0d17;
  }
}
</style>
