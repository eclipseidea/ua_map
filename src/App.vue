<template>
  <div id="app">
    <MapUA/>
  </div>
</template>

<script>
import MapUA from './components/MapUa.vue'

export default {
  name: 'App',
  components: {
    MapUA
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
  margin: 0 0;

}
</style>
