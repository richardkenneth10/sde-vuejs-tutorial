<script setup>
import { ref } from 'vue';
import ChildCompForProps from '../components/ChildCompForProps.vue';

const greeting = ref('Hello from parent');
</script>

<template>
  <ChildCompForProps :msg="greeting" />
</template>
