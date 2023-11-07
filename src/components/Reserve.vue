<template>
  <div class="feedback">
        <h3>聽聽別人的感想</h3>
        <ul class="feedback-item" >
            <li v-for="(item,key) in reviews" :key="key">
                <img :src="item.img" :alt="item.img">
                <p>{{item.name}}<br><br>
                    {{item.review}}<br>
                    <span>-- {{item.title}}</span>
                </p>
            </li>
            <!-- <li>
                <img src="img/avatar_2.png" alt="avater2">
                <p>廟口小霸王<br><br>
                    自從吃了這家餐廳以後，我口水連續流了一個多月都沒停，下次不要再被我遇到，不然我一定連他們桌子都啃下去。<br>
                    <span>-- 產品經理</span>
                </p>
            </li>
            <li>
                <img src="img/avatar_3.png" alt="avater3">
                <p>春天也來了<br><br>
                    自從吃了這家餐廳以後，我口水連續流了一個多月都沒停，下次不要再被我遇到，不然我一定連他們桌子都啃下去。<br>
                    <span>-- 產品經理</span>
                </p>
            </li> -->
        </ul>
    </div>
    <div class="map">
        <h3>我們的位置不太夠坐<br>
            要不要先定位呢？</h3>
        <div class="map-item">
            <img src="img/Map.png" alt="map">
            <div class="input">
                <label for="name">姓名</label><br>
                <input type="text" placeholder="姓名" v-model="reserve.name">
                <br>
                <label for="phone">電話</label><br>
                <input type="number" placeholder="電話" v-model="reserve.phone"><br>
                <label for="email">信箱</label><br>
                <input type="text" placeholder="信箱" v-model="reserve.email"><br>
                <label for="peolpe">人數</label><br>
                <input type="number" placeholder="人數" v-model="reserve.people"><br>
                <div class="btn-item">
                    <input type="button" value="取消" class="btn btn-cancel">
                    <input type="button" value="送出" class="btn btn-enter">
                </div>
            </div>
        </div>
    </div>
</template>

<script>

export default {
  data () {
    return {
      reviews: [
        {
          img: 'img/avatar_1.png',
          name: '高雄一口吃',
          review: '自從吃了這家餐廳以後，我口水連續流了一個多月都沒停，下次不要再被我遇到，不然我一定連他們桌子都啃下去。',
          title: '產品經理'
        },
        {
          img: 'img/avatar_2.png',
          name: '廟口小霸王',
          review: '自從吃了這家餐廳以後，我口水連續流了一個多月都沒停，下次不要再被我遇到，不然我一定連他們桌子都啃下去。',
          title: '產品經理'
        },
        {
          img: 'img/avatar_3.png',
          name: '春天也來了',
          review: '自從吃了這家餐廳以後，我口水連續流了一個多月都沒停，下次不要再被我遇到，不然我一定連他們桌子都啃下去。',
          title: '產品經理'
        }
      ],
      reserve: {
        name: '',
        phone: '',
        email: '',
        people: 0
      }
    }
  },
  methods: {
  }
}
</script>
