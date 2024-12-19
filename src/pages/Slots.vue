<script setup>
import { ref } from 'vue';
import ChildCompForSlots from '../components/ChildCompForSlots.vue';

const msg = ref('from parent');
</script>

<template>
  <ChildCompForSlots>{{ msg }}</ChildCompForSlots>
</template>
