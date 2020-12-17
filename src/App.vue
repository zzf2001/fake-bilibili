<template>
  <div id="app">
<!--    <div style="height: 20px"></div>-->
    <LoginAndRegistered></LoginAndRegistered>
    <Search></Search>
    <play></play>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import LoginAndRegistered from "@/components/LoginAndRegistered";
import Search from "@/components/Search/Search";
import play from "@/components/play";
export default {
  name: 'App',
  components: {
 Search,LoginAndRegistered,play,
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

  /*font-family: MicrosoftYaHeiUI;*/
}
img{
  cursor: pointer;
}
button{
  cursor: pointer;
}
</style>
