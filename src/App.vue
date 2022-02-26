<template>
  <div id="app">
    <CButton
      color="primary">
      Button Pertama
    </CButton>
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Ryan Pazrin"/>
  </div>
</template>

<script>
import { CButton } from '@coreui/vue'
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    CButton
  }
}
</script>

<style lang="scss">
  // Import Main styles for this application
  @import 'assets/scss/style';

  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
</style>
