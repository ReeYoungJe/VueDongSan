<template>

  <div class="menu">
    <a v-for="menuItems in menu" :key="menuItems">
      {{ menuItems }}
    </a>
  </div>

  <Discount/>


  <Modal :apiData="apiData" :popModal="popModal" :item="item"/>
  <Card  :apiData="apiData" />

</template>

<script>
import data from './assets/data'
import Discount from "@/components/Discount";
import Card from "@/components/Card/Card";
import Modal from "@/components/Card/Modal";


export default {
  name: 'App',
  components: {
    Modal,
    Card, Discount,
  },
  data() {
    return {
      item: 0,
      apiData: data,
      popModal: false,
      menu: ['Home', 'Shop', 'About'],
    }
  },
  methods: {

  }
}

</script>

<style>
* {
}

a {
  color: #333;
  text-decoration: unset
}

img {
  width: 100%;
}

body {
  margin: 0;
  text-align: center;
}

div {
  box-sizing: border-box;
}

.black-bg {
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  padding: 20px;
}

.white-bg {
  width: 100%;
  background: white;
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
.box-re{padding:10px; border: 1px solid #333; margin: 15px;}
</style>
