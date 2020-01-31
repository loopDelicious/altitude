<template>
  <div class="intro">
    <div class="intro-contents">
      <h3>Altitude</h3>
      <ul class="intro-items">
        <li><a href="https://neal.fun/deep-sea/" target="_blank" rel="noopener">The Deep Sea</a></li>
        <li><a href="https://xkcd.com/482/" target="_blank" rel="noopener">Height</a></li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Intro'
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  text-align: center;
  color: rgb(44, 44, 84);
  font-size: 76px;
  font-weight: bold;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.intro {
  height: 100vh;
  width: 100%;
  display: flex;
  -webkit-box-align: center;
  align-items: center;
  -webkit-box-pack: center;
  justify-content: center;
  position: relative;
  z-index: 999;
}
.intro-contents {
  display: grid;
  grid-template-rows: repeat(2, auto);
  position: relative;
  bottom: 50px;
}
.intro-items {
  color: rgb(77, 77, 128);
  font-size: 26px;
  text-align: center;
  margin-top: 15px;
  font-family: Oswald, sans-serif;
}
</style>
