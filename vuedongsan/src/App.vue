<template>

  <!-- 모달창 :: S -->
  <div class="black-bg" v-if="modal == true">
    <div class="white-bg">
      <div class="close close-x" @click="modal = false"></div>
      <h4>상세페이지</h4>
      <p>내용</p>
    </div>
  </div>
  <!-- 모달창 :: E -->

  <div class="menu">
    <a v-for="item in menus" :key="item">{{item}}</a>
  </div>

  <!-- for문 사용하기 -->
  <div v-for="(item,index) in oneroom" :key="index">
    <img class="room-img" :src="item.image" :alt="index"/>
    <h4 @click="modal = true">{{item.title}}</h4>
    <p>{{item.content}}</p>
    <p>{{item.price}} 만원</p>
    <!-- <button v-on:click="increase(index)">허위매물신고</button> <span>신고수 : {{item.count}}</span> -->
  </div> 
  
</template>

<script>
/*
//js 파일의 apple 변수 사용하기 위해 작성 
//import apple from './oneroom.js'; //단건 가져오기
import {apple,apple2} from './oneroom.js';
apple2;
*/

import data from './oneroom.js';

export default {
  name: 'App',
  //데이터 보관함
  data(){
    //데이터는 object 자료로 저장 (예) {자료이름:자료내용})
    return {
      oneroom : data
      , modal : false
      , menus : ['Home', 'Shop', 'About']
      , lists : [{product:'역삼동원룸'
                      , count : 0
                      , img : require("./assets/room1.jpg")}
                    ,{product:'천호동원룸'
                      , count : 0
                      , img : require("./assets/room2.jpg")}
                    ,{product:'마포구원룸'
                      , count : 0
                      , img : require("./assets/room3.jpg")}]
    }
  },
  methods : {
    increase(index){
      this.lists[index].count += 1; //this : object를 의미
    }
  },
  components: {
  }
}
</script>

<style>
/* 모달창 :: S */
body{
  margin: 0;
}
.close {
  float:inline-end;
  width:50px;
  height:50px;
  text-align:center;
}
.close-x:after{
  content: "\00d7"; 
  font-size:25pt;
  line-height:45px;
}
div{
  box-sizing: border-box;
}
.black-bg{
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  padding: 20px;
}
.white-bg{
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}
/* 모달창 :: E */

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.menu{
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}
.menu a{
  color: white;
  padding: 10px;
}
.room-img{
  width: 100%;
  margin-top: 40px;
}
</style>
