<template>

  <div class="black-bg" v-if="modal == true">
    <div class="white-bg">
      <a href="" @click="modalClose()">닫기</a>
      <h4>상세페이지</h4>
      <p>상세페이지 내용</p>
    </div>
  </div>
  <div class="menu">
    <a v-for="menuItems in menu" :key="menuItems">{{ menuItems }}</a>
  </div>
  <div v-for="(productItems, idx)  in 3" :key="productItems">
    <img src="@/assets/room0.jpg">
    <h4 @click="modalOpen()">{{ products[idx] }} 원룸</h4>
    <p>{{ price[idx] }} 만원</p>
    <button @click="increase(idx);">허위매물신고</button><span>신고수 : {{counts[idx]}} </span>
  </div>

</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      modal: false,
      counts: [0,0,0],
      menu: ['Home', 'Shop', 'About'],
      price: ['60', '50', '40'],
      products: ['역삼동원룸', '천호동원룸', '마포구원룸']
    }
  },
  methods: {
    increase(idx){
     this.counts[idx] += 1;
    },
    modalOpen(){
      this.modal = true;
    },
    modalClose(){
      this.modal = false
    },
  }
}

</script>

<style>

body {
  margin : 0;
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
