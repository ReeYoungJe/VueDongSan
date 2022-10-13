<template>

  <div class="menu">
    <a v-for="menuItems in menu" :key="menuItems">
      {{ menuItems }}
    </a>
  </div>

  <div class="black-bg" v-if="modal == true" >
    <div class="white-bg">
      <img :src="apiData[index].image">
      <h4>{{apiData[index].title}}</h4>
      <p>{{ apiData[index].content }} </p>
      <a href="#" @click.prevent="modal = false">닫기</a>
    </div>
  </div>

  <div v-for="(productItems, idx)  in apiData" :key="productItems">
    <a href="#" @click.prevent="modal = true; index = idx">
      <img :src="apiData[idx].image">
      <p>매물번호 : {{ apiData[idx].id }} </p>
      <h4>{{ apiData[idx].title }}</h4>
      <p>{{ apiData[idx].content }} </p>
      <p>{{ apiData[idx].price }} 만원</p>
    </a>

  </div>

</template>

<script>
import data from './assets/data'
export default {
  name: 'App',
  data() {
    return {
      index : 0,
      apiData : data,
      modal: false,
      menu: ['Home', 'Shop', 'About'],
      price: ['60', '50', '40'],
      products: ['역삼동원룸', '천호동원룸', '마포구원룸']
    }
  },
  methods: {

  }
}

</script>

<style>
*{}
a{list-style: none; text-decoration: none; color:#333;}
img{width:100%; }
body {
  margin : 0;
  text-align: center;
}
div {
  box-sizing: border-box;
}
.black-bg {
  width: 100%; height:100%;
  background: rgba(0,0,0,0.5);
  position: fixed; padding: 20px;
}
.white-bg {
  width: 100%; background: white;
  border-radius: 8px;
  padding: 20px;
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
