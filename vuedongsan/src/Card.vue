<template>
    <!-- for문 사용하기 
    <div v-for="(item,index) in oneroom" :key="index">-->
    <div>
        <img class="room-img" :src="item.image" :alt="index"/>
        <!-- <h4 @click="modal = true; target = index">{{item.title}}</h4> -->
        <h4>{{item.title}}</h4>
        <p>{{item.content}}</p>
        <p>{{item.price}} 만원</p>
        <!-- <button v-on:click="increase(index)">허위매물신고</button> <span>신고수 : {{item.count}}</span> -->
    </div> 
</template>

<script>
export default {
    name : 'Card',
    props : {
        item : Object,
        index : Number
    }
}
</script>

<style>
.room-img{
  width: 100%;
  margin-top: 40px;
}
</style>