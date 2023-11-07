<template>
  <div class="log-frame">
    <img src="img/logo_l@svg.svg" alt="title">
    <h3>享受美食好味道</h3>
    <div class="checkout-box">
        <h3>Checkout List</h3>
        <ul class="item-header">
            <li>商品</li>
            <li>單價</li>
            <li>數量</li>
            <li>總計</li>
            <li>操作</li>
        </ul>
        <CheckoutItem v-for="(item,key) in products" :key="key" :product="item"
        />
        <!-- <ul class="item-header" v-for="(item,key) in products" :key="key">
            <li class="item-img">
                <img :src="item.img" :alt="item.img">
                <p class="name">{{ item.name }}<br>
                  <span>{{ item.engnName }}</span>
                </p>
            </li>
            <li class="price">${{ item.price }}</li>
            <li class="count">
                <font-awesome-icon :icon="['fas', 'circle-minus']" class="btn" @click="clickMinus(num=1)"/>
                <span class="num">{{ num }}</span>
                <font-awesome-icon :icon="['fas', 'circle-plus']" class="btn" @click="clickAdd"/>
            </li>
            <li class="amount">$300</li>
            <li class="operate">
                <font-awesome-icon :icon="['fas', 'trash']" class="btn" size="lg"/>
            </li>
        </ul> -->
    </div>
    <div class="btn">
      <p>總計：0元</p>
      <button class="btn-checkout">確認付款</button>
    </div>
  </div>

</template>

<script>
import CheckoutItem from '@/components/CheckoutItem.vue'
export default {
  data () {
    return {
      products: [],
      num: 1
    }
  },
  components: {
    CheckoutItem
  },
  // methods: {
  //   clickMinus () {
  //     this.count -= 1
  //   },
  //   clickAdd () {
  //     this.count += 1
  //   }
  // },
  inject: ['emitter'],
  mounted () {
    this.emitter.on('getData', (data) => {
      // this.products = data
      const { img, name, engName, price } = data
      console.log(img)
      console.log(name)
      console.log(engName)
      console.log(price)

      this.products.push({ img, name, engName, price })
    })
  }
}
</script>
