<template>
  <ul class="item-header">
      <!-- <li class="item-img">
          <img :src="product.img" :alt="product.img">
          <p class="name">{{product.name}}<br>
            <span>{{product.engName}}</span>
          </p>
      </li>
      <li class="price">${{product.price}}</li>
      <li class="count">
          <font-awesome-icon :icon="['fas', 'circle-minus']" class="btn" @click="clickMinus()"/>
          <span class="num">{{ count }}</span>
          <font-awesome-icon :icon="['fas', 'circle-plus']" class="btn" @click="clickAdd()"/>
      </li>
      <li class="amount">$300</li>
      <li class="operate">
          <font-awesome-icon :icon="['fas', 'trash']" class="btn" size="lg"/>
      </li> -->
      {{ products }}
  </ul>
  <div class="btn">
    <button class="btn-checkout">確認付款</button>
  </div>
</template>

<script>

export default {
  data () {
    return {
      count: 1
    }
  },
  props: [
    'product'
  ],
  methods: {
    clickMinus () {
      this.count -= 1
    },
    clickAdd () {
      this.count += 1
    }
  }
}
</script>
