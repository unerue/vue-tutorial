<template>
  <div class="black-bg" v-if="모달창열렸니 == true">
    <div class="white-bg">
      <h4>상세페이지임</h4>
      <p>상세페이지 내용임</p>
      <button @click="모달창열렸니 = false">닫기</button>
    </div>
  </div>

  <div class="menu">
    <a>Home</a>
    <a>Products</a>
    <a>About</a>
  </div>
  <div v-for="(동네, i) in products" :key="동네">
    <h4>{{ i+1 }} {{ 동네.title }}</h4>
    <button v-on:click="신고수++">허위매물신고</button><span>신고수: {{ 신고수 }}</span>
    <button @click="increase">구매</button>
  </div>
  <HelloWorld msg="Welcome to Your Vue.js App"/>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import data from './assets/data.js'

export default {
  name: 'App',
  data() {
    return {
      모달창열렸니: false,
      신고수: 0,
      // products: ['역삼동원룸', '천호동원룸', '마포구원룸']
      products: data
    }
  },
  methods: {
    increase() {
      this.신고수 += 1
    }
  },
  components: {
    // HelloWorld
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  /* margin-top: 60px; */
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
