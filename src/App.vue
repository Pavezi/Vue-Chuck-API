<template>
  <div id="app">
    <img src="./assets/logo.png">
    <ChuckNorrisComponent/>
  </div>
</template>

<script>
import ChuckNorrisComponent from './components/ChuckNorrisComponent'

export default {
  name: 'App',
  components: {
    ChuckNorrisComponent
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
