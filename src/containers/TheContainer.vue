<template>
  <div class="c-app">

    <CWrapper>
      <TheHeader />
      <div class="c-body">
        <main class="c-main">
          <CContainer fluid>
            <transition name="fade" mode="out-in">
              <!-- <router-view :key="$route.path"></router-view> -->
              <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Blanditiis dolor quisquam, molestiae aliquid laudantium fugiat ad inventore aut molestias earum voluptates a sequi nesciunt deleniti ratione ut consequuntur eligendi necessitatibus!</p>
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