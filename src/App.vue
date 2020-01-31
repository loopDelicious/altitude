<template>
  <div id="app">
    <Intro />
    <Items />
  </div>
</template>

<script>
import Intro from './components/Intro.vue'
import Items from './components/Items.vue'


export default {
  name: 'app',
  components: {
    Intro,
    Items
  }
}
</script>

<style>
#app {
  font-family: 'Roboto', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
