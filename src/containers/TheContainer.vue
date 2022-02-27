<template>
  <div class="c-app">

    <CWrapper>
      <div class="c-body">
        <main class="c-main">
          <CContainer fluid>
            <transition name="fade" mode="out-in">
              <!-- <router-view :key="$route.path"></router-view> -->
              <slot name="body">default</slot>
            </transition>
          </CContainer>
        </main>
      </div>
      <TheFooter />
    </CWrapper>
  </div>
</template>

<script>
import TheFooter from './TheFooter'

export default {
  name: 'TheContainer',
  components: {
    TheFooter
  }
}
</script>

<style>

</style>