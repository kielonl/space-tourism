<template>
  <button><h4>EXPLORE</h4></button>
</template>

<script setup lang="ts"></script>

<style scoped lang="scss">
button {
  background: #ffffff;
  border-radius: 50%;
  padding: 3em;
  outline: none;
  border: none;
  cursor: pointer;
  transition: all 300ms;
  &:hover {
    outline: 3em solid rgba(255, 255, 255, 10.36%);
  }
  h4 {
    color: #0b0d17;
  }
}
</style>
