<template>
  <div v-if="isModalOpen === true" class="black-bg">
    <div class="white-bg">
      <h4>{{ products[idx].title }}</h4>
      <p>{{ products[idx].content }}</p>
      <button @click="this.isModalOpen=false">X</button>
    </div>
  </div>

  <h1>원룸 샵</h1>
  <div class="menu">
    <a v-for="menu in menus" :key="menu">{{ menu }}</a>
  </div>
  <div v-for="room in products" :key="room">
    <img @click="this.isModalOpen=true; idx=room.id" :src="room.image" class="room-img">
    <h4 @click="this.isModalOpen=true; idx=room.id">{{ room.title }}</h4>
    <p>{{ room.price }}</p>
    <button @click="this.counts[room.id] += 1;">허위매물 신고</button>
    <span>신고수: {{ counts[room.id] }}</span>
  </div>
</template>

<script>

import data from './post.js';

export default {
  products: 'App',
  data() {
    return {
      idx: 0,
      counts: Array.from({length: data.length}, () => 0),
      menus: ['Home', 'Shop', 'About'],
      products: data,
      isModalOpen: false,

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

body {
  margin: 0
}

div {
  box-sizing: border-box;
}

.black-bg {
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  padding: 20px;
}

.white-bg {
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}
</style>
