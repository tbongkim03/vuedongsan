<template>

  <!-- 오늘의 5분 숙제 : 

  모달창 닫기버튼과 기능을 만들어오십시오.  -->
  <div class="black-bg" v-if="모달창열렸니 == true">
    <div class="white-bg">
      <!-- <h4>상세페이지임</h4> -->
      <h4>{{ 원룸들[상세페이지아이디].title }}</h4>
      <!-- <h4>상세페이지 내용임</h4>  -->
      <img :src="원룸들[상세페이지아이디].image" :alt="원룸들[상세페이지아이디].id">
      <p>{{ 원룸들[상세페이지아이디].price }} 원</p>
      <p>{{ 원룸들[상세페이지아이디].content }}</p>
      <span @click="모달창열렸니=false" style="align-self: flex-end;">닫기</span>
    </div>
    
  </div>






  <div class="menu">
    <a v-for="작명 in 메뉴들" :key="작명">{{ 작명 }}</a>
    <!-- <a href="">Home</a>
    <a href="">Products</a>
    <a href="">About</a> -->
  </div>


  <!-- <div class="discount">
    <h4>지금 결제하면 20% 할인</h4>
  </div> -->

  <!-- 컴포넌트 -->
  <Discount/>


  <!-- 오늘의 5분 숙제 : 

  v-for 문법을 이용해 지금 있는 상품목록을 반복문으로 축약해보십시오.

  가격은 신경쓰지말고 상품제목만 잘 보이면 됩니다. -->
  <div v-for="value in 원룸들" :key="value">
    <!-- <img :src="`src/assets/room${i}.jpg`" :alt="i" class="room-img"> -->
    <img :src="value.image" :alt="value.id" class="room-img">
    <!-- <h4 @click="모달창열렸니 = true">{{ value }}</h4> -->
    <h4 @click="모달창열렸니 = true; 상세페이지아이디 = value.id">{{ value.title }}</h4>
    <p>{{ value.price }} 원</p>
    <!-- 오늘의 5분 숙제 : 

    모든 상품에 신고버튼과 기능을 만들어오십시오.

    상품마다 각각 신고수를 따로 집계해야합니다. 그래서 신고수 3개를 각각 저장할 공간이 미리 필요하겠군요. -->
    <!-- <button @click="increase(i)">허위매물신고</button> <span>신고수 : {{ 신고수[i] }}</span> -->
  </div>
</template>

<script>

// import { isInDestructureAssignment } from 'vue/compiler-sfc';

 

// var 어레이 = [10,20,30];
// 어레이[0]

import oneroomdata from './assets/oneroom.js';
import Discount from './Discount.vue';

export default {
  name : 'App',
  data() {
    return {
      // 오늘의 5분 숙제 : 

      // 일단 이렇게 생긴 데이터를 하단에 하나 저장하십시오. 

      // products : ['역삼동원룸', '천호동원룸', '마포구원룸']
      products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
      메뉴들 : ['Home', 'Shop', 'About'],
      // 신고수 : [0, 0, 0],
      모달창열렸니 : false,
      원룸들 : oneroomdata,
      상세페이지아이디 : -1,
    }
  },
  methods: {
    increase(i) {
      this.신고수[i] ++;
    },
  },
  components : {
    Discount,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smooting: antialiased;
  -moz-osx-font-smooting: grayscale;
  text-align: center;
  color: 2c3e50;
}
.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}
.menu a {
  color: white;
  padding: 10px;
}

.room-img {
  width: 100%;
  margin-top: 40px;
}

/* 모달창 css */
body {
  margin: 0;
}
div {
  box-sizing: border-box;
}
.black-bg {
  width: 100%; height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed; padding: 20px;
}
.white-bg {
  width: 100%; background: white;
  border-radius: 8px;
  padding: 20px;
  display: flex;
  flex-direction: column;
}
/* .discount {
  background: #eee;
  padding: 10px;
  margin: 10px;
  border-radius: 5px;
} */
</style> 