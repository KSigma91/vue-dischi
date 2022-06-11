<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <header>
      <myHeader/>
    </header>

    <main>
      <myMain/>
    </main>
  </div>
</template>

<script>
//import axios from 'axios'
import myHeader from './components/myHeader.vue'
import myMain from './components/myMain.vue'

export default {
  name: 'App',
  components: {
    myHeader,
    myMain
}
}
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0 !important;
  padding: 0;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
