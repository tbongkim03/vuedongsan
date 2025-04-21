<template>

  <div>
    <!-- <img :src="`src/assets/room${i}.jpg`" :alt="i" class="room-img"> -->
    <img :src="원룸.image" :alt="원룸.id" class="room-img">
    <!-- <h4 @click="모달창열렸니 = true">{{ value }}</h4> -->
    
    <!-- 이거 어케 하지? -->
     <h4>{{ 원룸.title }}</h4>
    <!-- <h4 @click="모달창열렸니 = true; 상세페이지아이디 = value.id">{{ value.title }}</h4> -->
    
    
    <p>{{ 원룸.price }} 원</p>
    <!-- <button @click="increase(i)">허위매물신고</button> <span>신고수 : {{ 신고수[i] }}</span> -->
  </div>
</template>

<script>
export default {
  name: 'Card',
  props: {
    원룸 : Object,
  }
}
</script>

<style>

</style>