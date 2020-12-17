<template>

<div id="LoginAndRegistered">
  <div class="background">
    <img src="../assets/img/登录和注册/bilibili.png" height="89" width="199"/>
  </div>
  <div id="Relative">
    <div class="control">
      <button @click="login"  class="btn" :class="{  btn1 : isActive  , btn2: really} ">登录</button>
      <button @click="registered" class="btn" :class="{  btn1 : really  , btn2: isActive} ">注册</button>
    </div>
    <div>
      <keep-alive>
      <component v-bind:is="currentTabComponent"></component>
      </keep-alive>
    </div>
  </div>
</div>
</template>

<script>
import Login from "@/components/Login";
import Registered from "@/components/Registered";
export default {
name: "LoginAndRegistered",
  data(){
  return{
    isActive : true,
    really : false,
    currentTabComponent : Login,
  }
  },
  components:{
    Login,Registered,
  },
  methods:{
  login:function () {
    // console.log("dds")
    document.getElementsByClassName(this.button)
    this.isActive = true
    this.really = false
    this.currentTabComponent = Login
  },
    registered:function () {
      this.isActive = false
      this.really = true
      this.currentTabComponent = Registered

    }
  }
}

</script>

<style scoped>
#LoginAndRegistered{
  background-color: #343434;
  height: 1100px;
  position: relative;
}
.Relative{
  position: relative;
}
.control{
  width: 250px;
  position: absolute;
  top: 200px;
  left: 0;
  right: 0;
  margin: auto;
  display: flex;
  justify-content: space-around;

}
.btn1{
  color: #FFB100;

}
.btn2{
  color: #A3A3A3;
}
.btn{

  font-size: 40px;
  line-height: 43px;
  background-color: #343434;
  outline: none;
}
.background{
  background-image: url("../assets/img/登录和注册/xkxk.png");
  /*margin-left:25px ;*/
  height: 104px;

}
.background>img{
  position: absolute;
  left: 70px;
  top: 10px;
}
</style>
