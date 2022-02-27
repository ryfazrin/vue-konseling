<template>
  <div id="app">
    <TheContainer>
      <template v-slot:body>
        <CButton
          color="primary"
          variant="outline"
        >
          Button Pertama
        </CButton>
      </template>
    </TheContainer>
  </div>
</template>

<script>
import TheContainer from './containers/TheContainer.vue'

export default {
  name: 'App',
  components: {
    TheContainer,
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
