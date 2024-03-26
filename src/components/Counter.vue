<script setup>
import { ref } from 'vue';

const props = defineProps({
  initialValue: Number
})

const counter = ref(props.initialValue ?? 0);
</script>

<template>
  <div class="counter">
    <slot name="header"></slot>
    <div>
      <button @click="counter++">Increment</button>
      <span class="counter-text">{{ counter }}</span>
    </div>
    <slot name="footer"></slot>
  </div>
</template>

<style scoped>
.counter {
  background: #ccc;
  padding: 20px;
  border-radius: 5px;
}

.counter-text {
  margin-left: 10px;
}
</style>
