<template>
  
  <div class="menu">
    <a v-for="작명 in 메뉴들" :key="작명">{{ 작명 }}</a>
    <!-- <a href="">Home</a>
    <a href="">Products</a>
    <a href="">About</a> -->
  </div>
  <!-- 오늘의 5분 숙제 : 

  v-for 문법을 이용해 지금 있는 상품목록을 반복문으로 축약해보십시오.

  가격은 신경쓰지말고 상품제목만 잘 보이면 됩니다. -->
  <div v-for="(value, i) in products" :key="value">
    <h4>{{ value }}</h4>
    <p>50 만원</p>
    <!-- 오늘의 5분 숙제 : 

    모든 상품에 신고버튼과 기능을 만들어오십시오.

    상품마다 각각 신고수를 따로 집계해야합니다. 그래서 신고수 3개를 각각 저장할 공간이 미리 필요하겠군요. -->
    <button @click="increase(i)">허위매물신고</button> <span>신고수 : {{ 신고수[i] }}</span>
  </div>
</template>

<script>

import { isInDestructureAssignment } from 'vue/compiler-sfc';

 

// var 어레이 = [10,20,30];
// 어레이[0]

export default {
  name : 'App',
  data() {
    return {
      // 오늘의 5분 숙제 : 

      // 일단 이렇게 생긴 데이터를 하단에 하나 저장하십시오. 

      // products : ['역삼동원룸', '천호동원룸', '마포구원룸']
      products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
      메뉴들 : ['Home', 'Shop', 'About'],
      신고수 : [0, 0, 0],
    }
  },
  methods: {
    increase(i) {
      this.신고수[i] ++;
    }
  },
  components : {
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

</style> 