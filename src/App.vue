<template>
  <ModalVue @closeModal="isModalOpen=false" :room=selected :is-modal-open="isModalOpen" />
  <Menu/>
  <Discount/>
  <Card @openModal="isModalOpen=true" v-for="room in products" :key="room" :room="room"  @modifyRoom="selected=$event"/>
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
      counts: Array.from({length: data.length}, () => 0),
      products: data,
      isModalOpen: false,
      selected: Object
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

body {
  margin: 0
}

div {
  box-sizing: border-box;
}

</style>
