<template>

  <div class="menu">
    <a v-for="menuItems in menu" :key="menuItems">
      {{ menuItems }}
    </a>
  </div>

  <Discount/>
  <Card :item="item" :apiData="apiData" :popModal="popModal"/>

</template>

<script>
import data from './assets/data'
import Discount from "@/components/Discount";
import Card from "@/components/Card/Card";


export default {
  name: 'App',
  components: {
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
    increase(idx) {
      this.counts[idx] += 1;
    },
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
</style>
