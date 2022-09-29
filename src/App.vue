<template>
  <div class="menu">
    <a v-for="menuItems in menu" :key="menuItems">{{ menuItems }}</a>
  </div>
  <div v-for="(productItems, idx)  in 3" :key="productItems">
    <img src="@/assets/room0.jpg">
    <h4>{{ products[idx] }} 원룸</h4>
    <p>{{ price[idx] }} 만원</p>
    <button @click="increase(idx);">허위매물신고</button><span>신고수 : {{counts[idx]}} </span>
  </div>

</template>

<script>
export default {
  name: 'App',
  data() {
    return {

      counts: [0,0,0],
      menu: ['Home', 'Shop', 'About'],
      price: ['60', '50', '40'],
      products: ['역삼동원룸', '천호동원룸', '마포구원룸']
    }
  },
  methods: {
    increase(idx){
     this.counts[idx] += 1;
     console.log(this);
    },
  }
}

</script>

<style>


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
