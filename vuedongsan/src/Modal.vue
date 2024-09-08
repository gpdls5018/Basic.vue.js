<template>
<div class="black-bg" v-if="modal == true">
    <div class="white-bg">
        <!-- <div class="close close-x" @click="modal = false"></div> -->
        <img class="room-img" :src="oneroom[target].image" :alt="index"/>
        <h4>{{oneroom[target].title}}</h4>
        <p>{{oneroom[target].content}}</p>
        <p>{{oneroom[target].price}} 만원</p>
    </div>
</div>
</template>

<script>

export default {
    name : 'Modal', 
    props : {
        oneroom : Array //받아온 데이터의 자료형 입력
        , target : Number
        , modal : Boolean
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
</style>