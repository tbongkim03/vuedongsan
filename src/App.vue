<template>
  <img alt="Vue logo" src="./assets/logo.svg">
  <div>
    <h4>{{ products[0] }}</h4>
    <p>50 만원</p>
  </div>
  <div>
    <h4>{{ products[1] }}</h4>
    <p>가격 아무거나</p>
  </div>
  <div>
    <h4>{{ products[2] }}</h4>
    <p>가격 아무거나</p>
  </div>
</template>

<script>

 



export default {
  name : 'App',
  data() {
    return {
      // 오늘의 5분 숙제 : 

      // 일단 이렇게 생긴 데이터를 하단에 하나 저장하십시오. 

      // products : ['역삼동원룸', '천호동원룸', '마포구원룸']
      products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
    }
  },
  components : {
  }
}
</script>

<style>
</style> 