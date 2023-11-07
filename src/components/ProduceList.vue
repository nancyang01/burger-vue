<template>
  <div class="side-bar">
    <ul class="side-bar-item">
        <h3><font-awesome-icon :icon="['fas', 'leaf']" class="icon-leaf"/>
            線上訂購美食
        </h3>
        <li v-for="(item,key) in list" :key="key">
        <router-link to="#">{{item}}</router-link>
        </li>
    </ul>
    <div class="cart">
        <div class="search">
            <div class="search-bar">
                <input type="text" placeholder="搜尋餐點" v-model="searchText">
                <font-awesome-icon :icon="['fas', 'magnifying-glass']"  class="icon-search"/>
            </div>
            <div class="checkout">
                <router-link to="/Checkout">結帳去</router-link>
                <font-awesome-icon :icon="['fas', 'cart-shopping']"  class="icon-cart"/>
                <div class="cart-num">{{cartNum}}</div>
            </div>
        </div>
        <ul class="cart-item" >
            <li v-for="(item,key) in filterSearch" :key="key">
                <img :src="item.img" :alt="item.img">
                <h4>{{item.name}}</h4>
                <p class="title">{{item.engName}}</p>
                <p class="price">${{item.price}}</p>
                <a href="#" @click.prevent="clickToCart(item)"><font-awesome-icon :icon="['fas', 'cart-shopping']"  class="icon-cart"/> 加入購物車</a>
            </li>
        </ul>
    </div>
  </div>
</template>

<script>

export default {
  data () {
    return {
      products: [
        {
          img: 'img/product_1.png',
          name: '經典漢堡套餐',
          engName: 'Classic Hamburger Package',
          price: 120
        },
        {
          img: 'img/product_2.png',
          name: '英俊香腸',
          engName: 'Handsome Sausage',
          price: 80
        },
        {
          img: 'img/product_3.png',
          name: '漢堡兄弟',
          engName: 'Hamburg Brothers',
          price: 240
        },
        {
          img: 'img/product_4.png',
          name: '完美願望',
          engName: 'Dragon Ball Package',
          price: 300
        }
      ],
      list: ['全部', '只愛吃薯條', '加熱就可食', '不敗漢堡系列'],
      cartNum: 0,
      tempSelected: {},
      searchText: ''
    }
  },
  inject: ['emitter'],
  methods: {
    clickToCart (product) {
      this.tempSelected = {
        ...product
      }
      // console.log(this.tempSelected)
      this.emitter.emit('getData', this.tempSelected)
      // this.cartNum += 1
    }
  },
  computed: {
    filterSearch () {
      return this.products.filter((item) =>
        item.name.match(this.searchText)
      )
    }
  }
}
</script>
