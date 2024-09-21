<template>
  <div id="app">
    <VueCronometro />
  </div>
</template>

<script>
import VueCronometro from './components/Cronometro.vue';

export default {
  name: 'App',
  components: {
    VueCronometro
  }
};
</script>

<style>
@import '../public/style.css';
</style>
