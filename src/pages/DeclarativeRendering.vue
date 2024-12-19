<script setup>
import { ref, reactive } from 'vue';

// component logic
// declare some reactive state here.
const counter = reactive({ count: 0 });
const message = ref('Message');

counter.count++;
message.value = 'Dynamic message';
</script>

<template>
  <h1>Dynamic message: {{ message }}</h1>
  <p>Dynamic count: {{ counter.count }}</p>
</template>
