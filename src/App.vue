<template>
  <div id="app">
    <ButtonRedirect />
  </div>
</template>

<script>
import ButtonRedirect from "./components/ButtonRedirect.vue";

export default {
  name: "App",
  components: {
    ButtonRedirect,
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  height: 100vh; /* Make sure the app fills the full height of the viewport */
  display: flex;
  justify-content: center;
  align-items: center; /* These flex properties will center the button both horizontally and vertically */
}
</style>
