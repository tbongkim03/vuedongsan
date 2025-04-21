<template>
<!-- 오늘의 5분 숙제 : 

  v-for 문법을 이용해 지금 있는 상품목록을 반복문으로 축약해보십시오.

  가격은 신경쓰지말고 상품제목만 잘 보이면 됩니다. -->
  <div v-for="value in 원룸들" :key="value">
    <!-- <img :src="`src/assets/room${i}.jpg`" :alt="i" class="room-img"> -->
    <img :src="value.image" :alt="value.id" class="room-img">
    <!-- <h4 @click="모달창열렸니 = true">{{ value }}</h4> -->
    
    <!-- 이거 어케 하지? -->
    <!-- <h4 @click="모달창열렸니 = true; 상세페이지아이디 = value.id">{{ value.title }}</h4> -->
    
    
    <p>{{ value.price }} 원</p>
    <!-- 오늘의 5분 숙제 : 

    모든 상품에 신고버튼과 기능을 만들어오십시오.

    상품마다 각각 신고수를 따로 집계해야합니다. 그래서 신고수 3개를 각각 저장할 공간이 미리 필요하겠군요. -->
    <!-- <button @click="increase(i)">허위매물신고</button> <span>신고수 : {{ 신고수[i] }}</span> -->
  </div>
</template>

<script>
export default {
  name: 'Card',
  props: {
    원룸들 : Array,
  }
}
</script>

<style>

</style>