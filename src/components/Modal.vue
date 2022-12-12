<template>
  <div v-if="isModalOpen === true" class="black-bg">
    <div class="white-bg">
      <h4>{{ room.title }}</h4>
      <p>{{ room.content }}</p>
      <input v-model.number="month">
      <p>{{ month }} 개월 선택함: {{ month * room.price }} 원</p>
      <button @click="$emit('closeModal')">X</button>
    </div>
  </div>
</template>
<script>
export default {
  name: 'ModalVue',
  data() {
    return {
      month: 1,
    }
  },
  watch: {
    // 파라마터 첫번째 인자 -> 변경 후 , 두 번째 인자 -> 변경 전 인자
    month(input) {
      if(input > 13) {
        alert("13개월 이상 입력할 수 없습니다.");
        this.month = 1
      }
      const reg = /[ㄱ-ㅎ|ㅏ-ㅣ|가-힣|a-z]/;
      if(reg.test(input)) {
        alert("문자는 입력 불가능 합니다.");
        this.month = 1
      }
    }
  },
  props: {
    idx: Number,
    isModalOpen: Boolean,
    room: {
      title: String,
      content: String,
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