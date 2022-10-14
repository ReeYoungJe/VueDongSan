<template>

  <div v-for="(productItems, idx)  in apiData" :key="idx" class="box-re">
    <img :src="productItems.image">
    <p>매물번호 : {{ productItems.id  + 1}} </p>
    <h4 >{{ productItems.title }}</h4>
    <p>{{ productItems.content }} </p>
    <p>{{ productItems.price }} 만원</p>
  </div>
</template>

<script>


export default {
  name: "Card",

  props : {
    item : Number,
    apiData : Object,

  }
}
</script>

<style scoped>

</style>