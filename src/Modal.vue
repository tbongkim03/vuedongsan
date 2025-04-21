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
      <!-- 오늘의 5분 숙제 :
      모달창 닫기버튼 다시 만들기 -->
      <span @click="$emit('closeModal')" style="align-self: flex-end;">닫기</span>
    </div>
    
  </div>
</template>

<script>
export default {
    name : 'Modal',
    props : {
        원룸들 : Array,
        상세페이지아이디 : Number,
        모달창열렸니 : Boolean,
    }
}
</script>

<style>

</style>