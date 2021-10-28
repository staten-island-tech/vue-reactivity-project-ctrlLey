<template>
  <div id="app">
    <div class="outfit-view">
      <div class="view coat-view">
        coats
        <img :src="image" :alt="coatName">
      </div>
      <div class="view tops-view">tops</div>
      <div class="view bottoms-view">bottoms</div>
      <div class="view shoes-view">shoes</div>
      <div class="view accessories-view">accessories</div>
    </div>
    <div class="clothes-view">
      <div @click="displayTest(coats)" class="category coat">
        <p >Coat</p>
        <ul >
          <li v-show="show" @click="display(coat.coatImage)" v-for="coat in coats" :key="coat.coatName" >
           
            <img :src="coat.coatImage" alt=""></li>
        </ul>
      </div>
      <div @click="showClothes" class="category tops">
        <p>Tops</p>
        <ul>
          <li v-show="show" @click="display(coat.coatImage)"  v-for="coat in coats" :key="coat.coatName" >
            <img :src="coat.coatImage" alt="">
          </li>
        </ul>
      </div>
      <div class="category bottoms">Bottoms</div>
      <div class="category shoes">Shoes</div>
      <div class="category accessories">Accessories</div>
    </div>

  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  data () {
    return {
      show: true, 
      dTest: {
        coatsDisplay: null,
        topsDisplay: null,
      } ,
      image: ``,
      coats:
       [{display:false},
       {
        coatName: 'coat1',
        coatImage:'https://www.vuemastery.com/images/challenges/vmSocks-green-onWhite.jpg'
      },
       {
        coatName: 'coat2',
        coatImage:'https://www.vuemastery.com/images/challenges/vmSocks-blue-onWhite.jpg',
      }, {
        coatName: 'coat3',
        coatImage: 'https://www.vuemastery.com/images/challenges/vmSocks-green-onWhite.jpg',
      }],
    }
  },
  methods: {
    hideClothes : function () {
      this.show = false
    },
    showClothes: function () {
      this.show = true
    },
    displayTest(clothes) {
      this.show = clothes.display
    },
    // this doesnt work lmao
    // it does the opposite
    display(coatImage) {
      this.image= coatImage
    }

  }
  /* components: {
    HelloWorld
  } */
}
</script>

<style lang="scss">
.hide {
  display: none;
}
ul {
  list-style: none;
  margin: 0 auto;
  padding: 0;
}

img {
  height: 3rem;
}
.outfit-view {
  display: flex;
  flex-direction: column;
  width: 65%;
  height: 80vh;
  flex-wrap: wrap;
  background-color: bisque;
  
}
.view {
  display: flex;
  background-color: peachpuff;
  width: 10rem;
  height: 10rem;
  border: gray .25rem solid;
  justify-content: center;
  align-items: center;
  margin: 1rem auto;
  text-align: center;

}


.clothes-view {
  display: flex;
  flex-direction: column;
  width: 30%;
  background-color: lavender;
}
.category {
  // display: flex;
  background-color: lightblue;
  width: 40%;
  padding: .5rem 0rem;
  border: gray .25rem solid;
  justify-content: center;
  align-items: center;
  margin: .5rem auto;
  text-align: center;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  display: flex;
  flex-direction: row;
  justify-content: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
