<script setup>
import { ref } from 'vue';
import ChildCompForEmits from '../components/ChildCompForEmits.vue';

const childMsg = ref('No child msg yet');
</script>

<template>
  <ChildCompForEmits @response="(msg) => (childMsg = msg)" />
  <p>{{ childMsg }}</p>
</template>
