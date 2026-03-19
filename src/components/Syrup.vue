<template>
  <div class="syrup" :style="{ backgroundColor: currentSyrup.color }"></div>
</template>

<script setup lang="ts">
import { currentSyrup } from "../stores/beverage";
</script>

<style lang="scss" scoped>
.syrup {
  transform: translateY(400%);
  position: relative;
  width: 100%;
  height: 20%;
  animation: pour-tea 2s 1s forwards;
  z-index: 2;
  transition: background-color 0.5s ease;
}
</style>
