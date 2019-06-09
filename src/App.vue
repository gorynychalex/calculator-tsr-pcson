<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo_pcson.png">
    <!--<HelloWorld msg="Welcome to Your Vue.js App"/>-->
    <Equipment/>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import Equipment from './components/Equipment.vue'

export default {
  name: 'app',
  components: {
    // HelloWorld,
    Equipment
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
