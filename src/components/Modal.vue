<template>
  <div v-if="isModalOpen === true" class="black-bg">
    <div class="white-bg">
      <h4>{{ room.title }}</h4>
      <p>{{ room.content }}</p>
      <input v-model.number="count">
      <p>{{count}} 개월 선택함 : {{ room.price * count }}</p>
      <button @click="$emit('closeModal')">X</button>
    </div>
  </div>
</template>
<script>
export default {
  name: 'ModalVue',
  data() {
    return {
      count: 1,
    }

  },
  props: {
    idx: Number,
    isModalOpen: Boolean,
    room: {
      title: String,
      content: String,
      price: Number
    },
  }
}
</script>
<style>

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