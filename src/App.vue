<template>
  <div id="app">
    <img src="./assets/logo.png">
    <!-- <hello></hello> -->
    <Thumbs></Thumbs>
  </div>
</template>

<script>
// import hello from './components/HelloWorld'
import Thumbs from './components/Thumbs'
export default {
  name: 'App',
  components: {
    // hello,
    Thumbs

  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
