<template>
  <div class="discount">
    <h4>지금 결제하면 {{ discounting }}% 할인</h4>
  </div>
</template>

<script>
export default {
  name: 'Discount',
  props : {
    discounting : Number,
  }
}
</script>

<style>
.discount {
  background: #eee;
  padding: 10px;
  margin: 10px;
  border-radius: 5px;
}
</style>