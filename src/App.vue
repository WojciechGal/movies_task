<template>
  <div id="app">
    <RatingCalculator/>
  </div>
</template>

<script>
import RatingCalculator from "./components/RatingCalculator";

export default {
  name: 'App',
  components: {
    RatingCalculator
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background-image: url(./assets/images/k-m.jpg);
  background-size: cover;
  height: 100%;
  overflow: hidden;
}
</style>
