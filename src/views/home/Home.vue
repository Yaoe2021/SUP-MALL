<template>
  <nav-bar class="home-nav"><div slot="center">购物街</div></nav-bar>
</template>

<script>
import NavBar from '../../components/navbar/NavBar.vue'
export default {
  components:{
  NavBar
  }
}
</script>

<style>
.home-nav{
  background-color: pink;
  color: white;
}
</style>