<template>
  <div id="app" class="wrapper-app">
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
    .wrapper-app {
        font-family: Verdana, Geneva, Tahoma, sans-serif;
        padding: 22px 44px;
    }
</style>
