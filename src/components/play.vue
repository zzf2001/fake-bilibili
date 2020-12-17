<template>
<div id="play">
  <div class="relative">
    <div class="center">
      <h1 class="font1">{{title}}</h1>
      <div class="play">
        <div class="foutbuttom">

          <img src="../assets/img/播放页面/声音+点击效果.png" alt="" class="img1">
          <img src="../assets/img/播放页面/设置.png" alt="" class="img1">
          <img src="../assets/img/播放页面/下载.png" alt="" class="img1">
          <img src="../assets/img/播放页面/转发-空.png" alt="" class="img1">
        </div>
        <div class="playing" @dblclick="disappear">
          <img src="../assets/img/播放页面/居中暂停键.png" alt="" class="img2" :class="{ disappear : dis }" @click="appear">
        </div>
        <div class="time">
          <div class="timecontorl" :style=" {left : position}" ></div>
        </div>
        <div class="playbottom">
          <div class="bottomTop">
            <img src="../assets/img/播放页面/小栏暂停键.png" alt="" class="smallstop">
            <span class="timeshow">{{ago}}/{{all}}</span>
          </div>
          <div class="relative1">
            <p class="font2">{{people}}人在看 ，{{comment}}条弹幕</p>
            <div class="bottomcenter">


              <img src="../assets/img/播放页面/打赏.png" height="36" width="35" alt=""/>
              <img src="../assets/img/播放页面/点赞+已点击效果.png" height="34" width="40"/>
              <img src="../assets/img/播放页面/全屏.png" height="33" width="40"/>


              <img src="../assets/img/播放页面/转发-空.png" height="30" width="33"/></div>
            <div class="publish">
              <input type="text" class="playinput">
              <button class="publishbtn">发表</button>
            </div>
          </div>
        </div>
      </div>
      <div class="information">
        <div class="infleft">
          <img :src="infimg" alt="" class="infimg">
          <span class="Span"><h3>{{infname}}</h3>
          <button>+关注</button></span>
        </div>
        <div class="intright">
          <p>个性签名：{{sign}}</p>
        </div>
      </div>
      <div class="recommend">
        <h1 class="reh">推荐视频</h1>
        <ul>
          <li class="recommendli" v-for="(item,index) in a" :key="index">
            <img :src="item.img" alt="" class="reimg">
            <div class="lidiv">
              <img src="" alt="">
              {{item.people}}
              <span class="lileft"><img src="" alt="">{{item.long}}</span>
            </div>
            <img src="../assets/img/播放页面/赞.png" alt="" class="recommendimg">
            <p>{{item.tilte}}</p>
            <p>{{item.pag}}</p>
          </li>
        </ul>
      </div>
      <div class="Comment">
        <h1 class="Comh">评论</h1>
        <textarea name="comment" id="" cols="30" rows="10" placeholder="留下善意的评论吧..."></textarea>
        <button>发表</button>
      </div>
      <div class="box">
      <div class="othercomment" v-for="(item,index) in b" :key="index">
          <div class="comleft">
            <img :src="item.img" alt="" class="comimg">
            <span class="Span"><h3>{{item.name}}</h3>
            <div class="look">lv:{{item.lv}}</div></span>
          </div>
          <div class="comright">
            <p class="commendp">：{{item.comment}}</p>
          </div>
        <div class="good">
          <img src="../assets/img/播放页面/赞.png" alt="">
          <img src="../assets/img/播放页面/踩.png" alt="">
        </div>
        </div>
      </div>
      <div class="swich">
        <span>&lt;</span>
        <button class="spesical swichbtn">1</button>
        <button class="swichbtn">2</button>
        <button class="swichbtn">3</button>
        <button class="swichbtn">4</button>
        <p>...</p>
        <button class="swichbtn">10</button>
        <span>&gt;</span>
      </div>
    </div>
    <div class="LeftandRighe">
      <div class="relative">
          <div class="ear">
            <img src="../assets/img/播放页面/小左耳朵.png" height="19" width="28"/>
            <img src="../assets/img/播放页面/小右耳朵.png" height="20" width="26"/>
          </div>
        <ul>
          <li>数码</li>
          <li>生活</li>
          <li>美食</li>
          <li>鬼畜</li>
          <li>时尚</li>
          <li>资讯</li>
          <li>娱乐</li>
          <li>专栏</li>
          <li>电影</li>
          <li>TV</li>
        </ul>
      </div>
    </div>
    <div class="RightandLeft">
      <div class="relative">
        <div class="ear">
          <img src="../assets/img/播放页面/小左耳朵.png" height="19" width="28"/>
          <img src="../assets/img/播放页面/小右耳朵.png" height="20" width="26"/>
        </div>
        <ul>
          <li>直播</li>
          <li>动画</li>
          <li>番剧</li>
          <li>国创</li>
          <li>漫画</li>
          <li>音乐</li>
          <li>舞蹈</li>
          <li>游戏</li>
          <li>知识</li>
          <li>课堂</li>
        </ul>
      </div>
    </div>
  </div>
</div>
</template>

<script>
export default {
name: "play",
  data(){
  return{
    title:'【爱特之光】我们都是未来B站创始人',
    dis : false,
    position: '200px',
    all:'40:00',
    ago:'10:54',
    people:'1111',
    comment:'111',
    infimg:require('../assets/img/播放页面/路人头像.png'),
    infname:'web-zzf',
    sign:'可能有一天，我们会因为各种各样的原因，告别英雄联盟。就好像太一失去了 亚古兽一样。但是我一直坚信，我们终会再见。',
    a:[
      {
        img:require('../assets/img/播放页面/选图.png'),
        tilte:'【数码宝贝 X 英雄联盟】 ',
        pag:'被选中的召唤师们，并肩作战',
        people:'100' ,
        long:'01:22:59'
      },
      {
        img:require('../assets/img/播放页面/选图.png'),
        tilte:'【数码宝贝 X 英雄联盟】 ',
        pag:'被选中的召唤师们，并肩作战',
        people:'100' ,
        long:'01:22:59'
      },
      {
        img:require('../assets/img/播放页面/选图.png'),
        tilte:'【数码宝贝 X 英雄联盟】 ',
        pag:'被选中的召唤师们，并肩作战',
        people:'100' ,
        long:'01:22:59'

      },
      {
        img:require('../assets/img/播放页面/选图.png'),
        tilte:'【数码宝贝 X 英雄联盟】 ',
        pag:'被选中的召唤师们，并肩作战',
        people:'100' ,
        long:'01:22:59'

      }
    ],
    b:[
      {
        img:require('../assets/img/播放页面/头像.png'),
        name:'路人甲',
        lv:'15',
        comment:'咱不知道说啥好，就给大家表演个才艺吧：胸口碎大石！！！吹爆？？吹爆。',
      },
      {
        img:require('../assets/img/播放页面/头像.png'),
        name:'路人甲',
        lv:'15',
        comment:'这不火吗！不比马保国好？赶快火起来！！',
      },
      {
        img:require('../assets/img/播放页面/头像.png'),
        name:'路人甲',
        lv:'15',
        comment: '年轻人你不讲武德？？我劝你耗子尾汁耗子尾汁。小心我闪电五连鞭抽你~~我一鞭，两鞭，三鞭。啊不，武林要以和为贵，要讲武德，不要搞窝里斗，谢谢朋友们。 '
      }
    ]
  }

  },
  methods:{
  appear(){
    this.dis = true
  },
  disappear(){
    this.dis = false
  }
  }
}

</script>

<style scoped>
#play{
  background-color:  #343434;
  height: 1900px;
}
  .relative{
    position: relative;
  }
  .center{
    width: 1025px;
    position: absolute;
    left: 0;
    right: 0;
    margin:auto;
  }
  .font1{
    margin-top: 77px;
    color: #FDF6F8;
    font-size: 28px;
  }
  .play{
    margin-bottom: 50px;
  }
  .foutbuttom{
    text-align: right;
    background-color: #474646;
    padding: 12px 0;
    align-items: center;
    margin-top: 50px;
  }
  .img1{
    margin-right: 20px;
    height: 24px;
  }
  .playing{
    height: 454px;
    background-color: #242424;
    position: relative;
  }
  .img2{
    position: absolute;
    right: 0;
    top: 0;
    bottom: 0;
    left: 0;
    margin:auto;
    cursor: pointer;
  }
  .disappear{
    opacity: 0;
    transition: all 0.1s;
  }
.LeftandRighe{
  width: 82px;
  height: 419px;
  background: #242424;
  border: 1px solid #434343;
  border-radius: 24px;
  padding-top:15px ;
  box-sizing: border-box;
  position: absolute;
  left:91px;
  top: 250px;
}
.ear{
  width: 60px;
  position: absolute;
  top: -35px;
  left: 0;
  right: 0;
  margin: auto;
}
.relative>ul>li
{
  color: #FDF6F8;
  text-align: center;
  font-size: 19px;
  line-height: 39px;
}
.RightandLeft{
  width: 82px;
  height: 419px;
  background: #242424;
  border: 1px solid #434343;
  border-radius: 24px;
  padding-top:15px ;
  box-sizing: border-box;
  position: absolute;
  right:91px;
  top: 250px;
}
.time{
  height: 12px;
  background-color: #343435;
  position: relative;
}
.timecontorl{
  width: 12px;
  height: 12px;
  background: #D9D6D6;
  border-radius: 50%;
  position: absolute;

}
.playbottom{
  width: 1022px;
  height: 92px;
  background: #242424;
  box-shadow: 1px 5px 12px 1px rgba(0, 0, 0, 0.21);
  border-radius: 2px;
  position: relative;
  /*padding:15px ;*/
  /*box-sizing: border-box;*/
}
.bottomTop{
  height: 40px;
}
.timeshow{
  position: absolute;
  right: 15px;
  top: 5px;
  font-size: 16px;
  color: #D9D6D6;
}
.smallstop{
  position: absolute;
  left: 15px;
  top: 15px;
  margin: auto;
  /*display: flex;*/
}
.font2{
  color: #6F6F6F;
  font-size: 18px;
  margin-left: 15px;
  margin-top:15px  ;
}
.bottomcenter{
  width: 300px;
  position: absolute;
  right: 0;
  top: 0;
  left: 0;
  bottom: 0;
  margin:auto;
  display: flex;
  justify-content: space-around;
}
.relative1{
  position: relative;
  display: flex;
}
.playinput{
  width: 285px;
  height: 45px;
  background: #242424;
  border: 1px solid #434343;
  border-radius: 24px;
outline: none;
  position: absolute;
  right: 40px;
  top: -10px;
  padding-left:25px ;
  font-size: 25px;
}
.publishbtn{
  width: 93px;
  height: 50px;
  background: #FFB100;
  box-shadow: 0 0 9px 1px rgba(112, 109, 101, 0.74);
  border-radius: 24px;
  position: absolute;
  right: 40px;
  top: -10px;


}
.infleft{
  display: flex;
}
h3{
  color: #FFFFFF;
  font-size: 21px;
  /*margin-left: 15px;*/
  text-align: center;
}
span>button{
  width: 69px;
  height: 25px;
  background: #FFB100;
  border-radius: 12px;
  position: absolute;
  right: 0;
  left: 0;
  top: 35px;
  margin: auto;
  color: #FFFFFF;
  font-size: 16px;
}
.Span{
  width: 120px;
  position: relative;

}
.intright{
  width: 700px;
  padding: 20px;
  color: #938E8E;
}
.information{
  display: flex;
  justify-content: space-around;
  height: 120px;
}
.infimg{
  width: 68px;
  height: 69px;
}
.recommend{
  height: 300px;
}
.recommend>ul{
  display: flex;
  justify-content: space-around;
  text-align: center;
}
.reimg{
  width: 206px;
  cursor: pointer
}
.reh{
  margin: 22px;
  color: white;
  font-size: 21px;
}
.recommend>ul>li>p{
  color: white;
  font-size: 16px;
  line-height: 28px;
  ;
}
.recommendli{
  position:relative;
}
.lidiv{
  position: absolute;
  top: 125px;
  color: white;
  font-size: 9px;
  box-sizing: border-box;
  padding-left: 20px;

}
.lileft{
  margin-left:110px ;

}
.Comh{
  margin-left: 20px;
  color: #FFFFFF;
}
.Comment>textarea{
  margin-top: 20px;
  width: 1026px;
  height: 98px;
  background: #414141;
  border-radius: 16px;
  outline: none;
  box-sizing: border-box;
  padding: 20px;
  resize:none;
  font-size: 20px;
  position: absolute;
  color: white;
}

textarea::placeholder{
  color: white;
  font-size: 16px;
}
.Comment{
  position: relative;
  height: 220px;
}
.Comment>button{
  width: 78px;
  height: 32px;
  background: #FFB100;
  border-radius: 16px;
  font-size: 16px;
  position: absolute;
  right: 20px;
  top: 110px;
  color: white;

}
.othercomment{
  display: flex;
  height: 120px;
  position: relative;
}
.comimg{
  width: 53px;
  height: 54px;
}
.comleft{
  display: flex;
}
.comright{
  width: 700px;
  padding: 10px 20px;
  color: #938E8E;
}
.look{
  width: 33px;
  height: 14px;
  background: #F9D011;
  /*border: 1px solid #FB7299;*/
  border-radius: 7px;
  position: absolute;
  right: 0;
  left: 0;
  top: 35px;
  margin: auto;
  color: #FFFFFF;
  font-size: 11px;
  text-align: center;
  /*padding: 5px;*/
}
.commendp{
  color: white;
  font-size: 16px;
}
.box{
  /*height: 500px;*/
}
.good{
  position: absolute;
  right: 25px;

}
.good>img{
  margin: 10px;
}
.swich{
  display: flex;
  color: white;
  font-size: 24px;
}
.swichbtn{
  width: 31px;
  height: 34px;

  border-radius: 8px;
  background-color:  #343434;
  color: white;
  font-size: 24px;
  outline: none;
}
.spesical{
  background-color:#F9D011 ;
}
.recommendimg{
  width: 12px;
  position: absolute;
  left: 10px;
  top: 125px;
}
.relative>ul>li{
  cursor: pointer;
}
</style>
