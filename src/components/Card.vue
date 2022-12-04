<template>
  <div>
    <img @click="$emit('openModal'); $emit('modifyRoom', room)" :src="room.image" class="room-img">
    <h4 @click="$emit('openModal'); $emit('modifyRoom', room)">{{ room.title }}</h4>
    <p>{{ room.price }}</p>
  </div>
</template>
<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'Card',
  props: {
    idx: Number,
    room: {
      image: String,
      title: String,
      price: Number
    },
  }
}

</script>
<style>

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

</style>