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