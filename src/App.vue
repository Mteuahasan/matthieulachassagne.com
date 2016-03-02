<template>
  <div id="app">
    <identity></identity>
    <projects :show="show"></projects>
  </div>
</template>

<script>
import Identity from './components/Identity'
import Projects from './components/Projects'

export default {
  components: {
    Identity,
    Projects
  },
  data () {
    return {
      show: false
    }
  },
  events: {
    'toggle-overlay': function (show) {
      this.show = show
    }
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
