<template>
  <div id="app">
<!--    <div style="height: 20px"></div>-->
    <LoginAndRegistered></LoginAndRegistered>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

import LoginAndRegistered from "@/components/LoginAndRegistered";
export default {
  name: 'App',
  components: {
    LoginAndRegistered,
  }
}
</script>

<style>
*{
  padding: 0;
  margin: 0;
  text-decoration: none;
  list-style: none;
  border: none;
}
</style>
