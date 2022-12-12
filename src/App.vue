<template>
  <Transition name="fade">
    <ModalVue @closeModal="isModalOpen=false" :room=selected :is-modal-open="isModalOpen"/>
  </Transition>

  <Menu/>
  <Discount/>

  <button @click="ascSort()">가격 낮은 순 정렬</button>
  <button @click="descSort()">가격 높은 순 정렬</button>
  <button @click="alphaSort()">가나다 순 정렬</button>
  <button @click="originalSort()">원래대로 정렬</button>
  <Card @openModal="isModalOpen=true" v-for="room in products" :key="room" :room="room" @modifyRoom="selected=$event"/>
</template>

<script>
import data from './post.js';
import Discount from "@/components/DiscountBanner.vue";
import Menu from "@/components/MenuBar.vue";
import ModalVue from "@/components/Modal.vue";
import Card from "@/components/Card.vue";

export default {
  products: 'App',
  data() {
    return {
      idx: 0,
      originalData: [...data],
      counts: Array.from({length: data.length}, () => 0),
      products: data,
      isModalOpen: false,
      selected: Object,
    }
  },
  methods: {
    ascSort() {
      this.products.sort((a, b) => {
        return a.price - b.price;
      });
    },
    descSort() {
      this.products.sort((a, b) => {
        return b.price - a.price;
      });
    },
    alphaSort() {
      this.products.sort((a, b) => {
        if (a.title > b.title) return 1;
        else return -1;
      });
    },
    originalSort() {
      this.products.sort((a, b) => {
        return a.id - b.id;
      });
    }
  },
  components: {Card, ModalVue, Discount, Menu}
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

.fade-leave-from {
  opacity: 1;
}

.fade-leave-to {
  opacity: 0;
}

.fade-leave-active {
  transition: 0.5s;
}

.fade-enter-from {
  transform: translateY(-1000px);
}

.fade-enter-active {
  transition: all 1s;
}

.fade-enter-to {
  transform: translateY(0px);
}

body {
  margin: 0
}

div {
  box-sizing: border-box;
}

</style>
