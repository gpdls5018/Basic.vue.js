<template>

  <!-- 모달창 :: S -->
  <Modal :oneroom="oneroom" v-bind:target="target" :modal="modal"/>
  <!-- 모달창 :: E -->

  <div class="menu">
    <a v-for="item in menus" :key="item">{{item}}</a>
  </div>

  <Discount v-bind="object"/> <!--하단과 동일-->
  <!-- <Discount :name="object.name" :age="object.age"/> -->

  <Card v-for="(item,index) in oneroom" :key="index" :item="item" :index="index"/>
  
</template>

<script>
/*
//js 파일의 apple 변수 사용하기 위해 작성 
//import apple from './oneroom.js'; //단건 가져오기
import {apple,apple2} from './oneroom.js';
apple2;
*/

import data from './oneroom.js';
import discount from './Discount.vue'
import modal from './Modal.vue'
import card from './Card.vue'

export default {
  name: 'App',
  //데이터 보관함
  data(){
    //데이터는 object 자료로 저장 (예) {자료이름:자료내용})
    return {
      object : {name : 'kim', age : 20}
      , oneroom : data
      , target : 0
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
  //메소드 등록
  methods : {
    increase(index){
      this.lists[index].count += 1; //this : object를 의미
    }
  },
  //컴포넌트 등록
  components: {
    Discount : discount,
    Modal : modal,
    Card : card
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
</style>
