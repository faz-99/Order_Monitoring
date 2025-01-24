<template>
  <img alt="Vue logo" src="https://zarashahjahan.com/cdn/shop/files/ZSJ_500x@2x.png?v=1614297380">
  <OrderMonitor/>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
import OrderMonitor from './components/OrderMonitor.vue'

export default {
  name: 'App',
  components: {
   // HelloWorld,
    OrderMonitor
  }
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
