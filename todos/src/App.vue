<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Vue Study 해봅시다."/>
    <TestPage text="Vue Study"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import TestPage from './components/TestPage.vue';

export default {
  name: 'App',
  components: {
    HelloWorld,
    TestPage
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
  margin-top: 60px;
}
</style>
