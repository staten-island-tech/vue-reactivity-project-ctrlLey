<template>
  <div id="app">
    <div class="outfit-view">
      <div class="view coat-view">
        coats
        <img :src="coatView" :alt="coats.coatName">
      </div>
      <div class="view tops-view">
        tops
        <img :src="image" :alt="coats.coatName">
        </div>
      <div class="view bottoms-view">bottoms</div>
      <div class="view shoes-view">shoes</div>
      <div class="view accessories-view">accessories</div>
    </div>
    <div class="clothes-view">
      <div class="category coat">
        <p @click="showCoats(display.coatsDisplay)" class="category-title">Coat</p>
        <ul>
          <li class="items" v-show="display.coatsDisplay" @click="displayCoatView(coat.coatImage)" v-for="coat in coats" :key="coat.coatName" >
           <p>{{coat.coatName}}</p>
            <img :src="coat.coatImage" :alt="coat.coatName"></li>
        </ul>
      </div>
      <div  class="category tops">
        <p @click="showTops(display.topsDisplay)"
        class="category-title">Tops</p>
        <ul>
          <li class="items" v-show="display.topsDisplay" @click="displayImg(coat.coatImage)"  v-for="coat in coats" :key="coat.coatName" >
            <p>{{coat.coatName}}</p>
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
      show: false, 
      display: {
        coatsDisplay: null,
        topsDisplay: null,
        bottomsDisplay: null, 
        shoesDisplay: null, 
        accessoriesDisplay: null, 
      } ,
      coatView: ``,
      coats:
       [
         //{display:false},
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
    showCoats(el) {
      console.log(el)
      if(el!==true ) {
        this.display.coatsDisplay = true
        this.display.topsDisplay = false
        this.display.bottomsDisplay = false
        this.display.shoesDisplay = false
        this.display.accessoriesDisplay = false

      } else if (el===true) {
        this.display.coatsDisplay = false
      }
    },
    showTops(el) {
      console.log(el)
      if(el!==true ) {
        this.display.coatsDisplay = false
        this.display.topsDisplay = true
        this.display.bottomsDisplay = false
        this.display.shoesDisplay = false
        this.display.accessoriesDisplay = false

      } else if (el===true) {
        this.display.topsDisplay = false
      }
    },

    displayCoatView(coatImage) {
      this.coatView= coatImage
    },
    

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
.category-title {
  border-bottom: .25rem solid black;
  width: 40%;
  text-align: center;
  margin: 1rem auto;
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
