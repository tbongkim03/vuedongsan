<template>
    <!-- 오늘의 5분 숙제 : 
    
      모달창 닫기버튼과 기능을 만들어오십시오.  -->
    <div class="black-bg" v-if="모달창열렸니 == true">
        <div class="white-bg">
            <!-- <h4>상세페이지임</h4> -->
            <!-- <h4>상세페이지 내용임</h4>  -->
            <img :src="원룸들[상세페이지아이디].image" :alt="원룸들[상세페이지아이디].id">
            <h4>{{ 원룸들[상세페이지아이디].title }}</h4>
            <p>{{ 원룸들[상세페이지아이디].content }}</p>
            <!-- <input @input="month = $event.target.value"> -->
            <input v-model="month">
            <p> {{ month }} 개월 선택함 : {{ month * 원룸들[상세페이지아이디].price }} 원</p>
    
            <!-- 오늘의 5분 숙제 :
          모달창 닫기버튼 다시 만들기 -->
            <span @click="$emit('closeModal')" style="align-self: flex-end;">닫기</span>
        </div>
    
    </div>
</template>

<script>
export default {
    name: 'Modal',
    data() {
        return {
            month: 1,
        }
    },
    props: {
        원룸들: Array,
        상세페이지아이디: Number,
        모달창열렸니: Boolean,
    },
    // 오늘의 5분 숙제 : 

    // month라는 데이터 항목에 숫자가 아니라 문자가 들어오면 
    // "숫자만 입력하라"는 alert()창을 띄워주고 month의 초기값을 1로 다시 설정해봅시다.
    watch: {
        month(a) {
            // 문제 발생, 백스페이스도 안눌림.
            if (typeof a === "string") {
                alert("숫자만 입력하세요");
                this.month = 1;
            }
        }
    }
}
</script>

<style>

</style>