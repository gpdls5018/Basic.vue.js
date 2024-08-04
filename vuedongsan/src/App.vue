<template>

  <div class="menu">
    <a v-for="item in menus" :key="item">{{item}}</a>
  </div>

  <div v-for="product in products" :key="product">
    <h4>{{product}}</h4>
    <p>50 만원</p>
  </div>
</template>

<script>

export default {
  name: 'App',
  //데이터 보관함
  data(){
    //데이터는 object 자료로 저장 (예) {자료이름:자료내용})
    return {
      menus : ['Home', 'Shop', 'About']
      , products : ['역삼동원룸','천호동원룸','마포구원룸']
    }
  },
  components: {
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
