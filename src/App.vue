<script setup lang="ts">
import { ref } from 'vue';
import HelloWorld from './components/HelloWorld.vue';

const formated = ref('');

const format = (value) => {
  const toNumber = parseFloat(value.replace(',', ''));
  const handle = new Intl.NumberFormat('es-MX').format(toNumber);
  const toStr = handle.toString();
  value === '' ? (formated.value = '0') : (formated.value = toStr);
};
</script>

<template>
  <div>
    <input v-model="formated" type="text" @input="format(formated)" />
  </div>
  <HelloWorld msg="Vite + Vue" />
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
