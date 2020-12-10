<template>
  <div id="Login">
    <div class="Relative">
      <input type="text" class="iput iput1" placeholder="你的手机号/邮箱">
      <input type="text" class="iput iput2" placeholder="密码">

      <div class="control">
        <button class="btn1" @click="check" :class="{ unselected : isActive , selected : really }"><div class="hook" :class="{ btn2 : isActive, btn3 : really }"></div></button>
        <p><span>记住我</span><a href="">忘记密码 ?</a></p>
      </div>
      <div class="center">
        <button class="login">登录</button>
        <button class="registered">注册</button>
      </div>
      <div class="centerImg">
        <div class="top">
          <img src="../assets/img/登录和注册/微信.png" alt="" class="img">
          <img src="../assets/img/登录和注册/QQ.png" alt="" class="img">
          <h3>用其他方式登录</h3>
        </div>
      </div>
      <div class="bottom">
        <button class="btnlast" @click="check1" :class="{ color : choose }">√</button>
        <p class="last">我已阅读并同意<a href="" class="A">哔哩哔哩用户使用协议</a> 和 <a href="" class="A">哔哩哔哩隐私政策</a></p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
name: "Login",
  data(){
  return{
    isActive : true,
    really : false,
    choose : false
  }
  },
  methods:{
  check:function (){
    if( this.isActive === true  ){
        this.isActive = false
        this.really = true

    }
    else {
      this.isActive = true
      this.really = false
    }

  },
  check1 :function (){
    if( this.choose === true  )
    {
      this.choose = false
    }
    else{
      this.choose = true
     }
  }
  }
}
</script>

<style scoped>
#Login{
  position: relative;
}
.Relative
{
  position: relative;
}
.iput{
  width: 836px;
  height: 46px;
  background: #242424;
  border-radius: 30px;
  position: absolute;
  top: 261px;
  margin: auto;
  right: 0;
  left: 0;
  outline: none;
  padding: 20px;
  font-size: 26px;
  /*box-sizing: content-box;*/
  color: #929191 ;
}
.iput2{
  top: 380px;
  background-image: url("../assets/img/登录和注册/键盘.png") ;
  background-repeat: no-repeat;
  background-position-x: 790px;
  background-position-y: 22px;
}
.iput1{
  background-image: url("../assets/img/登录和注册/二维码.png") ;
  background-repeat: no-repeat;
  background-position-x: 790px;
  background-position-y: 22px;
}
.Relative>div>p{
  width: 736px;
  height: 25px;
  font-size: 26px;
  font-family: Microsoft YaHei;
  font-weight: 400;
  color: #929191;
  line-height: 46px;

}
.hook{
  width: 18px;
  height: 10px;

  box-sizing: content-box;
  transform: rotate(-45deg);
  /*padding: 5px;*/
 }
 .control{
   width: 750px;
   height: 25px;
   font-size: 26px;
   font-family: Microsoft YaHei;
   font-weight: 400;
   color: #929191;
   /*line-height: 46px;*/
   position: absolute;
   top: 506px;
   right: 0;
   left: 0;
   margin: auto;
   display: flex;

 }
p{
  /*width: 736px;*/
  /*height: 25px;*/
  /*font-size: 26px;*/
  /*font-family: Microsoft YaHei;*/
  /*font-weight: 400;*/
  /*color: #929191;*/
  /*!*line-height: 46px;*!*/
  /*position: absolute;*/
  /*top: 506px;*/
  /*right: 0;*/
  /*left: 0;*/
  /*margin: auto;*/

}
a{
  color: #FFB100;
  font-size: 26px;
  margin-left:500px;
}
.btn1{
  width: 31px;
  height: 31px;
  /*position: absolute;*/
  outline: none;
  margin-top: 10px;
  margin-right: 10px;
  padding: 0 5px 8px;
  /*background-color: #FFB100;*/
}
.btn2{
  border-bottom: 2px solid #A3A2A2;
  border-left: 2px solid #A3A2A2 ;
}
.btn3{
  border-bottom: 2px solid  #242424;
  border-left: 2px solid  #242424 ;
}
.selected{
  background-color: #FFB100 ;
  border: 1px #FFB100 solid;
  border-radius: 3px;
}
.unselected{
  background-color:#343434;
  border: 1px #A3A2A2 solid;
  border-radius: 3px;
}
.login{
  width: 250px;
  height: 64px;
  background: #FFB100;
  border-radius: 10px;
  font-size: 30px;
  font-family: Microsoft YaHei UI;
  font-weight: 400;
  color: #FFFFFF;
  line-height: 46px;
  outline: none;

}
.registered{
  width: 250px;
  height: 64px;
  background: #DBD8D8;
  border-radius: 10px;
  font-size: 30px;
  font-family: Microsoft YaHei UI;
  font-weight: 400;
  color: #343434;
  line-height: 46px;
  outline: none;
  margin-left:50px ;
}
.center{
  position: absolute;
  width: 550px;
  right: 0;
  left: 0;
  top: 600px;
  margin: auto;
}
.centerImg{
  position: absolute;
  width: 300px;
  right: 0;
  left: 0;
  top: 700px;
  margin: auto;


}
.top
{
  text-align: center;
  color: #A3A2A2;
}
.img{
  margin: 15px;

}
.A{
  margin: 0;
  font-size: 24px;
  /*font-size: 10px;*/
}
.btnlast{
  margin-top:10px ;
  font-size: 18px;
  font-family: Microsoft YaHei;
  font-weight: 400;
  color: #929191;
  width: 27px;
  height: 28px;
  border: 1px solid #A3A2A2;
  border-radius: 13px;
  background-color: #343434 ;
  outline: none;
  margin-left: 20px;



}
.color{
  color: #242424;
  background-color:#FFB100 ;
}
.bottom{
  font-size: 24px;
  width: 800px;
  text-align: center;
  position: absolute;
  right: 0;
  left: 0;
  top: 830px;
  margin: auto;
  display: flex;
}
.last{
  font-size: 24px;
}
</style>
