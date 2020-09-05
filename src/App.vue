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
  },
  methods: {
    playTrack() {
      const kmAudio = new Audio(require('./assets/music/k-m.mp3'))
      kmAudio.addEventListener('ended', function() {
        this.currentTime = 0;
        this.play();
      }, false);
      kmAudio.play();
    }
  },
  mounted() {
    this.playTrack()
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
