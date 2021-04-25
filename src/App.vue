<template>
  <div id="app">
    <pokemon />
  </div>
</template>

<script>
import Pokemon from "./instancias/Pokemon.vue";

export default {
  name: "app",
  components: {
    Pokemon,
  },
};
</script>

<style>
@import url("https://use.fontawesome.com/releases/v5.8.2/css/all.css");

body {
  margin: 0;
  padding: 0;
}
#app {
  background-color: rgb(158, 168, 168);
}
</style>
