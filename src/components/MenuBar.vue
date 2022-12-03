<template>
  <h1>원룸 샵</h1>
  <div class="menu">
    <a v-for="menu in menus" :key="menu">{{ menu }}</a>
  </div>
</template>
<script>
  export default {
    data() {
      return {
        menus: ['Home', 'Shop', 'About'],
      }
    }
  }
</script>
<style>

</style>