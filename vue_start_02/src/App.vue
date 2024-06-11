<template>
<div class="menu">
  <a v-for="(메뉴이름,i) in 메뉴들" :key="i">{{ 메뉴이름 }}</a>
</div>

<div class="black-bg" v-if="모달창열림 == true">
  <div class="white-bg">
    <h4>상세페이지</h4>
    <p>상세페이지 내용</p>
    <button @click="모달창열림 = false">닫기</button>
  </div>
</div>



  <div @click="모달창열림 = true" class="room">
    <img :src="원룸들[0].image"  class="room-img">
    <h4>{{원룸들[0].title}}</h4>
    <p>{{원룸들[0].price}}</p>
  </div>
    <div @click="모달창열림 = true" class="room">
    <img :src="원룸들[3].image"  class="room-img">
    <h4>{{원룸들[3].title}}</h4>
    <p>{{원룸들[3].price}}</p>
  </div>
    <div @click="모달창열림 = true" class="room">
    <img :src="원룸들[0].image"  class="room-img">
    <h4>{{원룸들[5].title}}</h4>
    <p>{{원룸들[5].price}}</p>
  </div>
 
</template>
<script>

import data from './assets/data.js' ;


export default {
  name: 'App',
  // 데이터 보관통
  data(){
    return {
      원룸들 : data,
      모달창열림: false,
      신고수 : [0,0,0],
      메뉴들 : ['Home','Products','About'],
      products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
    }
  },
  methods : {
    increase(){
      this.신고수 += 1;
    }
  },
  components: {

  }
}
</script>

<style>
body{
  margin: 0;
}
div{
  box-sizing: border-box;
}
.black-bg{
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed; padding: 20px;
}
.white-bg{
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}

.room-img {
  width: 80%;
  margin-top: 40px;
}

.room:hover {
cursor: pointer;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu{
  background-color: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}
.menu a {
color: white;
padding: 10px;
}
</style>
