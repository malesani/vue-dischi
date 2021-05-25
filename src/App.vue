<template>
  <div id="app">
    <header-comp/>
    <main-comp/>
  </div>
</template>

<script>

import MainComp from './components/MainComp.vue'
import HeaderComp from './components/HeaderComp.vue'


export default {
  name: 'App',
  components: {
    HeaderComp,
    MainComp
  }
}
</script>

<style lang="scss">
  @import "../node_modules/bootstrap/scss/bootstrap";
  #app{
    width: 100%;
    height: 100vh;
    li{
      list-style: none;
    }
  }
  
</style>
