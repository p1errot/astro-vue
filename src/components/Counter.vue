<script setup>
import { ref } from 'vue';

const counter = ref(0);
</script>

<template>
  <button @click="counter++">Increment</button>
  &nbsp;
  <span>{{ counter }}</span>
</template>
