<template>
  <h1>원룸 샵</h1>
  <div class="menu">
    <a v-for="menu in menus" :key="menu">{{ menu }}</a>
  </div>
  <div v-for="i in 3" :key="i">
    <img :src= "getSrc(i-1)" class="room-img">
    <p><strong>{{ products[i - 1] }}</strong></p>
    <p>{{ dic[i - 1] }}</p>
    <button @click="this.counts[i-1] += 1">허위매물 신고</button>
    <span>신고수: {{ counts[i - 1] }}</span>
  </div>
</template>

<script>

export default {
  products: 'App',
  data() {
    return {
      counts: [0, 0, 0],
      getSrc: function(index) {
        return require('./assets/room'+index+'.jpg');
      },
      menus: ['Home', 'Shop', 'About'],
      products: ['역삼동원룸', '천호동원룸', '상도동원룸'],
      dic: {
        역삼동원룸: '50',
        천호동원룸: '가격은 아무거나',
        상도동원룸: '가격은 아무거나',
      }
    }
  },
  components: {}
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;

}

.menu a {
  color: white;
  padding: 10px;
}

.room-img {
  width: 100%;
  margin-top: 40px;
}
</style>
