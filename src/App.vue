<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <Slider/>
  </div>
</template>

<script>
import Slider from './components/Slider.vue';

export default {
  name: 'app',
  components: {
    Slider,
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
}

html,
body {
  margin: 0;
  height: 100%;
  overflow: hidden;
}

body {
  position: fixed;
}

#app {
  height: 100vh;
  width: 100vw;
  position: relative;
}
</style>
