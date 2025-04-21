<template>

  <Modal :원룸들="원룸들" :상세페이지아이디="상세페이지아이디" :모달창열렸니="모달창열렸니"/>




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
  <Card /> 컴포넌트로 상품리스트 보여주기 -->
  <Card :원룸들="원룸들" />
  
</template>

<script>

// import { isInDestructureAssignment } from 'vue/compiler-sfc';

 

// var 어레이 = [10,20,30];
// 어레이[0]

import oneroomdata from './assets/oneroom.js';
import Discount from './Discount.vue';
import Modal from './Modal.vue';
import Card from './Card.vue';

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
    Modal,
    Card,
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