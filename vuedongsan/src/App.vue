<template>

  <!-- modal -->
  
  <transition name='fade'>
    <Modal @closeModal='modalState = 0' 
      :rooms='rooms'
      :modalState='modalState'
      :userClicked='userClicked'/>
  </transition>
  
  <div class='menu'>
    <a v-for='(a, i) in menu' :key="i">{{ a }}</a>
  </div>

  <Discount v-if="discountState === 1"/>

  <button @click="priceSort">가격순정렬</button>
  <button @click="reversePriceSort">가격역순정렬</button>
  <button @click="nameSort">이름순정렬</button>
  <button @click="sortBack">되돌리기</button>

  <Card @openModal='modalState = 1; userClicked = $event' v-for='(a, i) in rooms' :key='i' :a='a'/>
  
</template>



<script>
import roomData from './data.js';
import Discount from './components/Discount.vue';
import Modal from './components/Modal.vue';
import Card from './components/Card.vue';

export default {
  name: 'App',
  data() {
    return {
      roomsOrigin: [...roomData],
      rooms: roomData,
      userClicked: 0,
      modalState: 0,
      menu: ['Home', 'Shop', 'About'],
      products: ['역삼동원룸', '천호동원룸', '마포구원룸'],
      discountState: 1,
    }
  },
  methods: {
    priceSort() {
      this.rooms.sort((a ,b) => {
        return a.price - b.price;
      });
    },
    reversePriceSort() {
      this.rooms.sort((a ,b) => {
        return b.price - a.price;
      });
    },
    nameSort() {
      this.rooms.sort((a, b) => {
        if (a.title < b.title === true) return -1
        else return 1;
      })
    },
    sortBack() {
      this.rooms = [...this.roomsOrigin];
    }
  },

  mounted() {
    // setTimeout(() => {
    //   this.discountState = 0;
    // }, 2000);
  },
  components: {
    Discount,
    Modal,
    Card,
  }
}
</script>



<style>
.fade-enter-from {
  transform: translateY(-1000px);
}
.fade-enter-active {
  transition: all 1s;
}
.fade-enter-to {
  transform: translateY(0px);
}

body {
  margin: 0;
}

div {
  box-sizing: border-box;
}

.discount {
  background: #eee;
  padding: 10px;
  margin: 10px;
  border-radius: 10px;
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
