<template>
  <span class="astronaut" ref="el">🧑‍🚀</span>
</template>

<script setup>
import { useMouse } from "@vueuse/core";
import { computed, ref } from "vue";

const { x, y } = useMouse();
const el = ref();

const cssRotate = computed(() => {
  if (!el.value) return;

  const rect = el.value.getBoundingClientRect();
  const centerX = rect.left + rect.width / 2;
  const centerY = rect.top + rect.height / 2;
  const dx = x.value - centerX;
  const dy = y.value - centerY;
  const angle = Math.atan2(dy, dx);
  const deg = angle * (180 / Math.PI) + 90;

  return `rotate(${deg}deg)`;
});
</script>

<style scoped>
.astronaut {
  display: inline-block;
  transform-origin: center center;
  transform: v-bind(cssRotate);
}
</style>