<template>
  <div class="menu">
      <router-link to="/" class="logo_item">六角西餐廳</router-link>
      <ul class="menu_bar">
          <li><router-link to="/menu">餐點</router-link></li>
          <li><router-link to="/booking">訂位</router-link></li>
          <li><router-link to="/login">登入</router-link></li>
      </ul>
      <font-awesome-icon :icon="['fas', 'bars']" class="bar" @click.prevent="clickmenuShow"/>
  </div>
</template>

<script>
import $ from 'jquery'

export default {

  data () {
    return {

    }
  },
  methods: {
    clickmenuShow (e) {
      console.log('click')
      $('div.menu ul.menu_bar').toggleClass('menu-show')
    }
  }
}
</script>
