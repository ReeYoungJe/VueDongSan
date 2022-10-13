<template>
  <div v-for="(productItems, idx)  in apiData" :key="productItems">
    <!--    <a href="#" @click.prevent="dddd = true; item = idx">-->
    <img :src="apiData[idx].image">
    <p>매물번호 : {{ apiData[idx].id  + 1}} </p>
    <h4>{{ apiData[idx].title }}</h4>
    <p>{{ apiData[idx].content }} </p>
    <p>{{ apiData[idx].price }} 만원</p>
    <!--    </a>-->
  </div>
</template>

<script>


export default {
  name: "Card",

  props : {
    item : Number,
    popModal : Boolean,
    apiData : Array,

  }
}
</script>

<style scoped>

</style>