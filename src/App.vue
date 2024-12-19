<script setup>
import { ref, computed } from 'vue';
import NotFound from './pages/NotFound.vue';
import Home from './pages/Home.vue';
import DeclarativeRendering from './pages/DeclarativeRendering.vue';
import AttributesBinding from './pages/AttributesBinding.vue';
import EventListeners from './pages/EventListeners.vue';
import FormBindings from './pages/FormBindings.vue';
import ConditionalRendering from './pages/ConditionalRendering.vue';
import ListRendering from './pages/ListRendering.vue';
import ComputedProperty from './pages/ComputedProperty.vue';
import LifecycleAndTemplateRefs from './pages/LifecycleAndTemplateRefs.vue';
import Watchers from './pages/Watchers.vue';
import Components from './pages/Components.vue';
import Props from './pages/Props.vue';
import Emits from './pages/Emits.vue';
import Slots from './pages/Slots.vue';
import Done from './pages/Done.vue';

const routes = {
  '/': Home,
  '/declarative-rendering': DeclarativeRendering,
  '/attributes-binding': AttributesBinding,
  '/event-listeners': EventListeners,
  '/form-bindings': FormBindings,
  '/conditional-rendering': ConditionalRendering,
  '/list-rendering': ListRendering,
  '/computed-property': ComputedProperty,
  '/lifecycle-and-template-refs': LifecycleAndTemplateRefs,
  '/watchers': Watchers,
  '/components': Components,
  '/props': Props,
  '/emits': Emits,
  '/slots': Slots,
  '/done': Done,
};

const currentPath = ref(window.location.hash);

window.addEventListener('hashchange', () => {
  currentPath.value = window.location.hash;
});

const currentView = computed(() => {
  return routes[currentPath.value.slice(1) || '/'] || NotFound;
});
</script>

<template>
  || <a href="#/">Home</a> ||
  <br />
  <a href="#/declarative-rendering">Declarative Rendering</a> |
  <a href="#/attributes-binding">Attributes Binding</a> |
  <a href="#/event-listeners">Event Listeners</a> |
  <a href="#/form-bindings">Form Bindings</a> |
  <a href="#/conditional-rendering">Conditional Rendering</a> |
  <a href="#/list-rendering">List Rendering</a> |
  <a href="#/computed-property">Computed Property</a> |
  <a href="#/lifecycle-and-template-refs">Lifecycle and Template Refs</a> |
  <a href="#/watchers">Watchers</a> | <a href="#/components">Components</a> |
  <a href="#/props">Props</a> | <a href="#/emits">Emits</a> |
  <a href="#/slots">Slots</a>
  <br />
  || <a href="#/done">Done</a> ||
  <br />
  <component :is="currentView" />
</template>
