<template>
  <div id="app">
    <Items />
    <Intro />
  </div>
</template>

<script>
import Intro from './components/Intro.vue'
import Items from './components/Items.vue'

export default {
  name: 'app',
  components: {
    Items,
    Intro
  },
  mounted () {
    window.scrollTo(0, document.body.clientHeight);
    // eslint-disable-next-line no-console
    // console.log("scrolling to bottom");
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
