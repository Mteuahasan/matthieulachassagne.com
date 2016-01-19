<template>
  <div id="app">
    <identity></identity>
    <slider></slider>
  </div>
</template>

<script>
import Identity from './components/Identity'
import Slider from './components/Slider'

export default {
  components: {
    Identity,
    Slider
  }
}
</script>

<style>
body {
  font-family: "Lato", sans-serif;
  font-style: normal;
  font-weight: 300;
  font-size: 13px;
  margin: 0;padding: 0;
  height: 100%;
}
html {
  height: 100%;
}
#app {
  height: 100%;
}
</style>
