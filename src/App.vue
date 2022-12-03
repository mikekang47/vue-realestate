<template>
  <h1>원룸 샵</h1>
  <div class="menu">
    <a v-for="menu in menus" :key="menu">{{menu}}</a>
  </div>

  <div v-for="room in products" :key="room">
    <p><strong>{{room}}</strong></p>
    <p>{{dic[room]}}</p>
  </div>
</template>

<script>

export default {
  products: 'App',
  data() {
    return {
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
</style>
