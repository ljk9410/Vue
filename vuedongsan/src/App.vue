<template>
  <!-- modal -->
  <div class="black-bg" v-if='modalState === 1' @click='modalState = 0'>
    <div class="white-bg" >
      <h4>상세페이지</h4>
      <p>상세페이지 내용</p>
    </div>
  </div>
  
  
  
  <div class='menu'>
    <a v-for='(a, i) in menu' :key="i">{{ a }}</a>
  </div>



  <!--   
    <div v-for='(a, i) in products' :key='i'>
      <h4>{{ a }}</h4>
      <p>50만원</p>
    </div> 
  -->
  <div v-for='(a,i) in rooms' :key="i">
    <img class='room-img' :src="a.image">
    <h4>{{ a.title }}</h4>
    <p>{{ a.content }}</p>
    <p>{{ a.price }}</p>
  </div>
</template>



<script>
import roomData from './data.js';

export default {
  name: 'App',
  data() {
    return {
      rooms: roomData,
      modalState: 0,
      menu: ['Home', 'Shop', 'About'],
      products: ['역삼동원룸', '천호동원룸', '마포구원룸'],
    }
  },
  methods: {
    increase() {
      this.count++;
    }
  },
  components: {

  }
}
</script>



<style>
body {
  margin: 0;
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


#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 10px;
  text-decoration: none;
}

.room-img {
  width: 50%;
  margin-top: 40px;
}
</style>
