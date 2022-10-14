<template>
<div class="black-bg" v-if="popModal == true" >
    <div class="white-bg">
      <img :src="apiData[item].image">
      <h4>{{apiData[item].title}}</h4>
      <p>{{ apiData[item].content }} </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Modal",
  props : {
    apiData : Array,
    item:Number,
    popModal: Boolean,


  }
}
</script>

<style scoped>

</style>