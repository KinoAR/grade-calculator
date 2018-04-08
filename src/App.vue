<template>
  <div id="app" class="container">
    <img src="./assets/logo.png">
    <Main/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld'
import Main from "./components/Main";

export default {
  name: 'App',
  components: {
    Main
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

.grade-row {
  margin-bottom: 15px;
}
</style>
