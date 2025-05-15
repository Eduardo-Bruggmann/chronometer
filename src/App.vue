<template>
  <div id="app">
    <VueChronometer />
  </div>
</template>

<script>
import VueChronometer from "./components/Chronometer.vue";

export default {
  name: "App",
  components: {
    VueChronometer,
  },
};
</script>

<style>
@import "../public/style.css";
</style>
