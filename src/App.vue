<template>
  <NavBar></NavBar>
  <Banner></Banner>
  <router-view></router-view>
  <Footer></Footer>
</template>

<script>
import emitter from '@/methods/emitter.js'
import NavBar from '@/components/NavBar.vue'
import Banner from '@/components/Banner.vue'
import Footer from '@/components/Footer.vue'
export default {
  components: {
    NavBar,
    Banner,
    Footer
  },
  provide () {
    return {
      emitter
    }
  }
}
</script>

<style lang="scss">
@import "./assets/css/all.scss";

</style>
