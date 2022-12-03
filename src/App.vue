<template>
  <h1>원룸 샵</h1>
  <div>
    <h4>{{products[0]}}</h4>
    <p>{{dic[products[0]]+'만원'}}</p>
  </div>
  <div>
    <h4>{{products[1]}}</h4>
    <p>{{dic[products[1]]}}</p>
  </div>
  <div>
    <h4>{{products[2]}}</h4>
    <p>{{dic[products[2]]}}</p>
  </div>

</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      products : ['역삼동원룸', '천호동원룸', '상도동원룸'],
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
</style>
