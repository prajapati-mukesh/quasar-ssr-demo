<template>
  <q-page class="flex flex-center">
    <div class="q-pa-md">
      <h2>React Component Demo</h2>
      <ReactCounter :initialCount="5" />
    </div>
  </q-page>
</template>

<script setup lang="ts">
import { ref, onMounted } from 'vue';
import Counter from '../react-components/Counter';

const ReactCounter = ref(null);

onMounted(async () => {
  const veaury = await import('veaury');
  ReactCounter.value = veaury.applyReactInVue(Counter);
});
</script>

<style scoped>
.q-page {
  padding: 20px;
}
</style>
