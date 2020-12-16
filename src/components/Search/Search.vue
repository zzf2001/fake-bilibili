<template>
<div id="Search">
  <div id="max">
    <div >
      <div class="top">
        <div class="center">
          <img :src="tv" alt="" class="move">
          <img :src="blibli" alt="" class="move">
          <input type="text" class="iput">
        </div>
      </div>
      <div class="relative">
        <ul class="firstul">
          <li v-for="(item,index) in li " :key="index" class="li"  @mouseenter="hover(index)" @mouseleave="reduction" :class="{firstcheck: really}">{{item}}</li>
        </ul>
        <div class="slid">
          <div class="transform" :style="change"></div>
        </div>
      </div>
      <div class="underslid">
        <img src="../../assets/img/搜索界面/筛选(1).png" height="21" width="18" class="underimg"/><span>筛选</span>
       <img src="../../assets/img/搜索界面/列表式排列.png" height="23" width="23" class="underimg"/>
        <img src="../../assets/img/搜索界面/方格排列.png" height="23" width="24" class="underimg"/></div>
     </div>
    <ul>
      <li class="repeat" v-for="(item,index) in first" :key="index">{{item}}</li>
    </ul>
    <ul>
      <li class="repeat" v-for="(item,index) in secend" :key="index">{{item}}</li>
    </ul>
    <ul >
      <li class="special repeat" v-for="(item,index) in third" :key="index">{{item}}</li>
    </ul>
    <div class="footer">
      <div class="eightdiv" v-for="(item,index) in eight" :key="index">
        <img :src="item.img" alt="" class="img">
        <h1 class="font1">{{item.title}}</h1>
        <h1 class="font2">
          <img :src="item.person" alt="">
          作者：{{item.people}}
        </h1>
        <h1 class="font3">
          <img :src="item.palyimg" alt="">
          {{item.play}}
          <img :src="item.timeimg" alt="" class="left">
          {{item.time}}
          <img :src="item.goodimg" alt="" class="left">
          {{item.good}}
        </h1>
      </div>
    </div>
    <div class="switch">


    </div>
  </div>
</div>
</template>

<script>
export default {
name: "Search",
  data(){
  return{
    tv: require('../../assets/img/搜索界面/bilibili-line.png'),
    blibli:require('../../assets/img/搜索界面/BILIBILI_LOGO.png'),
    li:['综合','视频 99+','番剧 0','影视 5','直播 0','专栏 99+','频道 99+','用户 99+'],
    judge1:[ false ,true,false,false,false,false,false,false ],
    n:0,
    pos:[30,195,370,545,720,895,1070,1245],
    check:0,
    really : false,
    first:['综合排序','最多点击',"最多发布",'最多弹幕','最多收藏'],
    secend:['全部时长','10分钟以下','10~30分钟','30~60分钟','60分钟以上'],
    third:['全部分区','动画','番剧','国创','音乐','舞蹈','游戏','数码','生活','美食','鬼畜','时尚','资讯','娱乐','影视','纪录片','电影','电视剧','其他'],
    eight:[

      {
        img:require('../../assets/img/图片/2.jpg'),
        title:'慎入！千万不要在网络上搜索这些词……',
        person:require('../../assets/img/搜索界面/个人 (4).png'),
        worker:'作者',
        people:'web无敌',
        palyimg:require('../../assets/img/搜索界面/播视web_播放量.png'),
        play:'5.6万',
        timeimg:require('../../assets/img/搜索界面/历史时间-2.png'),
        time:'2001-1-1',
        goodimg:require('../../assets/img/搜索界面/点赞.png'),
        good:'121'

      },
      {
        img:require('../../assets/img/图片/1.jpeg'),
        title:'慎入！千万不要在网络上搜索这些词……',
        person:require('../../assets/img/搜索界面/个人 (4).png'),
        worker:'作者',
        people:'UI无敌',
        palyimg:require('../../assets/img/搜索界面/播视web_播放量.png'),
        play:'5.6万',
        timeimg:require('../../assets/img/搜索界面/历史时间-2.png'),
        time:'2001-1-1',
        goodimg:require('../../assets/img/搜索界面/点赞.png'),
        good:'121'

      },
      {
        img:require('../../assets/img/图片/3.jpg'),
        title:'慎入！千万不要在网络上搜索这些词……',
        person:require('../../assets/img/搜索界面/个人 (4).png'),
        worker:'作者',
        people:'UI无敌',
        palyimg:require('../../assets/img/搜索界面/播视web_播放量.png'),
        play:'5.6万',
        timeimg:require('../../assets/img/搜索界面/历史时间-2.png'),
        time:'2001-1-1',
        goodimg:require('../../assets/img/搜索界面/点赞.png'),
        good:'121'

      },
      {
        img:require('../../assets/img/图片/4.jpg'),
        title:'慎入！千万不要在网络上搜索这些词……',
        person:require('../../assets/img/搜索界面/个人 (4).png'),
        worker:'作者',
        people:'UI无敌',
        palyimg:require('../../assets/img/搜索界面/播视web_播放量.png'),
        play:'5.6万',
        timeimg:require('../../assets/img/搜索界面/历史时间-2.png'),
        time:'2001-1-1',
        goodimg:require('../../assets/img/搜索界面/点赞.png'),
        good:'121'

      },
      {
        img:require('../../assets/img/图片/5.jpeg'),
        title:'慎入！千万不要在网络上搜索这些词……',
        person:require('../../assets/img/搜索界面/个人 (4).png'),
        worker:'作者',
        people:'UI无敌',
        palyimg:require('../../assets/img/搜索界面/播视web_播放量.png'),
        play:'5.6万',
        timeimg:require('../../assets/img/搜索界面/历史时间-2.png'),
        time:'2001-1-1',
        goodimg:require('../../assets/img/搜索界面/点赞.png'),
        good:'121'

      },
      {
        img:require('../../assets/img/图片/10.jpg'),
        title:'慎入！千万不要在网络上搜索这些词……',
        person:require('../../assets/img/搜索界面/个人 (4).png'),
        worker:'作者',
        people:'UI无敌',
        palyimg:require('../../assets/img/搜索界面/播视web_播放量.png'),
        play:'5.6万',
        timeimg:require('../../assets/img/搜索界面/历史时间-2.png'),
        time:'2001-1-1',
        goodimg:require('../../assets/img/搜索界面/点赞.png'),
        good:'121'

      },
      {
        img:require('../../assets/img/图片/11.jpg'),
        title:'慎入！千万不要在网络上搜索这些词……',
        person:require('../../assets/img/搜索界面/个人 (4).png'),
        worker:'作者',
        people:'UI无敌',
        palyimg:require('../../assets/img/搜索界面/播视web_播放量.png'),
        play:'5.6万',
        timeimg:require('../../assets/img/搜索界面/历史时间-2.png'),
        time:'2001-1-1',
        goodimg:require('../../assets/img/搜索界面/点赞.png'),
        good:'121'

      },
      {
        img:require('../../assets/img/图片/8.jpg'),
        title:'慎入！千万不要在网络上搜索这些词……',
        person:require('../../assets/img/搜索界面/个人 (4).png'),
        worker:'作者',
        people:'UI无敌',
        palyimg:require('../../assets/img/搜索界面/播视web_播放量.png'),
        play:'5.6万',
        timeimg:require('../../assets/img/搜索界面/历史时间-2.png'),
        time:'2001-1-1',
        goodimg:require('../../assets/img/搜索界面/点赞.png'),
        good:'121'

      },


    ]
  }
  },
  methods:{
  hover(index) {
    this.n = index


},
    reduction: function () {
    this.n = this.check


}
  },


 computed:{
  change:function (){
    return{
      left:this.pos[this.n] + 'px'
    }
  }
  }
}
</script>

<style scoped>
#Search{
  height: 1000px;
  background-color: #343434;

}
#max{
position: absolute;
  width: 1400px;
  right: 0;
  left: 0;
  margin:auto;
}
.top{
  height: 100px;
}
.center{
  position: absolute;
  width: 750px;
  top: 15px;
  left: 0;
  right: 0;
  margin: auto;
  display: flex;
}
.iput{
  width: 483px;
  height: 53px;
  background: #707070;
  box-shadow: 0 1px 2px 0 rgba(208, 240, 249, 0.35);
  border-radius: 10px;
  margin:12px 0 0 56px ;

}
.move{
  margin-left:15px ;
}
.li{
  color: #FFFFFF;
  width: 180px;
  text-align: center;
}
.firstul{
  display: flex;
  justify-content: space-around;
  height: 30px;
  /*border-bottom: 2px solid #A3A3A3;*/
}
/*.firstcheck{*/
/*  color: #FFB100;*/
/*}*/
.slid{
  width: 1400px;
  height: 2px;
  background-color: #A3A3A3 ;

}
.transform{
  position: absolute;
  width: 120px;
  height:3px;
  background-color: #FFB100;
  left: 180px;
  transition: all 0.5s;

}
.relative{
  position: relative;
}
span{
  color:#FFB100 ;
}
.underslid{
  margin-top: 15px;
}
ul{
  display: flex;
}
.repeat{
  width: 94px;
  height: 23px;
  border-radius: 10px;
  text-align: center;
  margin-top: 5px;
  color: #868686;

}
.special:nth-child(1)
{
  margin-left: 10px;
}

.color{
  background-color:#FFB100 ;
  color: #868686;
}
.footer{
  width: 1400px;
  display: flex;
  /*justify-content: space-around;*/
  flex-wrap: wrap;
  justify-content: space-between;
}
.eightdiv{
  width: 320px;
  height: 250px;
  background-color: #242424;
  overflow-wrap: break-word;
  margin-top: 30px;
  /*padding: 20px;*/
  /*box-sizing: border-box;*/
  cursor: pointer;
}
.img{
  width: 320px;
  height: 170px;
}
.font1{
  font-size: 14px;
  color: white;
  padding-left: 15px ;
}
.font2{
  color: #707070;
  font-size: 14px;
  padding-left: 15px;
  margin-top: 5px;
}
.font3{
  color: #707070;
  font-size: 14px;
  padding-left: 15px;
  margin-top: 10px;
}
.left{
  margin-left: 5px;
}
</style>
