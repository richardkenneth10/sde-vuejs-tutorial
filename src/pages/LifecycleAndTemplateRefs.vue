<script setup>
import { ref, onMounted } from 'vue';

const pElementRef = ref(null);

onMounted(
  () =>
    (pElementRef.value.textContent =
      'Updated Hello via a hook using a template ref')
);
</script>

<template>
  <p ref="pElementRef">Hello</p>
</template>
