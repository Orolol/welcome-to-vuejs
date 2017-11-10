<template>
  <div id="app">
    <contactView> </contactView>
  </div>
</template>

<script>
import contactView from './views/contactView'

export default {
  name: 'app',
  components: {
    contactView
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
