<template>
 <div id="Registered">
   <div class="position">
     <input type="text" class="iput" placeholder="昵称">
     <input type="text" class="iput" placeholder="设置密码（6-20位，含有字母和数字）">
     <input type="text" class="iput" placeholder="手机号/邮箱">
     <input type="text" class="iput" placeholder="验证码">
     <button class="btn">注册</button>
     <div class="bottom">
       <button class="btnlast" @click="check1" :class="{ color : choose }">√</button>
       <p class="last">我已阅读并同意<a href="" class="A">哔哩哔哩用户使用协议</a> 和 <a href="" class="A">哔哩哔哩隐私政策</a></p>
     </div>
   </div>
 </div>
</template>

<script>
export default {
  name: "Registered",
  data(){
    return{
      choose: false
    }

  },
  methods:{
    check1 :function (){
      if( this.choose === true  )
      {
        this.choose = false
        console.log("asdasd")
      }
      else{
        this.choose = true
      }
    }
  }
}
</script>

<style scoped>
#Registered{
  text-align: center;
  position: relative;
}
.position{
  width: 900px;
  padding: 0 17px;
  position: absolute;
  top: 200px;
  right: 0;
  left: 0;
  margin: auto;
}
.iput{
  width: 836px;
  height: 46px;
  background: #242424;
  border-radius: 30px;
  margin-bottom:32px ;

  outline: none;
  padding: 20px;
  font-size: 26px;
  /*box-sizing: content-box;*/
  color: #929191 ;
}
.btn{
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
  margin-top: 30px;
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
}
.color{
  color: #242424;
  background-color:#FFB100 ;
}
a{
  color: #FFB100;
  font-size: 26px;
  margin-left:500px;
}
.bottom{
  font-size: 24px;
  width: 800px;
  text-align: center;
  position: absolute;
  right: 0;
  left: 0;
  top: 630px;
  margin: auto;
  display: flex;
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
.A{
  margin:0;
  font-size: 24px;
}
.last{
  font-size: 24px;
  color:  #929191;
}
p{
  margin-left: 25px;
  margin-top: 10px;
}
</style>
