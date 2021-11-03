<template>
  <div id="app">

    <div class="outfit-view">
      <div class="view coat-view">
        <p class="fixed">coats</p>
        <img class="view-img" :src="outfitView.coatsView" :alt="coats.coatName">
      </div>
      
      <div class="view tops-view">
        <p class="fixed">tops</p>
        <img class="view-img" :src="outfitView.topsView" :alt="tops.topName">
      </div>
      <div class="view bottoms-view">
        <p class="fixed">bottoms</p>
        <img class="view-img" :src="outfitView.bottomsView" :alt="bottoms.bottomName">
      </div>
      <div class="view shoes-view">
        <p class="fixed">shoes</p>
        <img class="view-img" :src="outfitView.shoesView" :alt="shoes.shoeName">
      </div>
      <div class="view accessories-view">
        <p class="fixed">accessories</p>
        <img class="view-img" :src="outfitView.accessoriesView" :alt="accessories.accessoryName">
      </div>
    </div>

    <div class="clothes-view">
      <div class="category coat">
        <p @click="showCoats(display.coatsDisplay)" class="category-title">Coat</p>
        <ul>
          <li class="items" v-show="display.coatsDisplay" @click="displayCoatView(coat.coatImage)" v-for="coat in coats" :key="coat.coatName" >
            <p>{{coat.coatName}}</p>
            <img :src="coat.coatImage" :alt="coat.coatName">
          </li>
        </ul>
      </div>
      <div class="category tops">
        <p @click="showTops(display.topsDisplay)" class="category-title">Tops</p>
        <ul>
          <li class="items" v-show="display.topsDisplay" @click="displayTopView(top.topImage)"  v-for="top in tops" :key="top.topName" >
            <p>{{top.topName}}</p>
            <img :src="top.topImage" :alt="top.topName">
          </li>
        </ul>
      </div>
      <div class="category bottoms">
        <p @click="showBottoms(display.bottomsDisplay)" class="category-title">Bottoms</p>
        <ul>
          <li class="items" v-show="display.bottomsDisplay" @click="displayBottomView(bottom.bottomImage)"  v-for="bottom in bottoms" :key="bottom.bottomName" >
            <p>{{bottom.bottomName}}</p>
            <img :src="bottom.bottomImage" :alt="bottom.bottomName">
          </li>
        </ul>
      </div>
      <div class="category shoes">
        <p @click="showShoes(display.shoesDisplay)" class="category-title">Shoes</p>
        <ul>
          <li class="items" v-show="display.shoesDisplay" @click="displayShoeView(shoe.shoeImage)"  v-for="shoe in shoes" :key="shoe.shoeName" >
            <p>{{shoe.shoeName}}</p>
            <img :src="shoe.shoeImage" :alt="shoe.shoeName">
          </li>
        </ul>
      </div>
      <div class="category accessories">
        <p @click="showAccessories(display.accessoriesDisplay)" class="category-title">Accessories</p>
        <ul>
          <li class="items" v-show="display.accessoriesDisplay" @click="displayAccessoryView(accessory.accessoryImage)"  v-for="accessory in accessories" :key="accessory.accessoryName" >
            <p>{{accessory.accessoryName}}</p>
            <img :src="accessory.accessoryImage" :alt="accessory.accessoryName">
          </li>
        </ul>
      </div>
      <p>none of these go together well </p>
      <p>i had no idea what images to use so...... Love Nikki clothing bc this is a poor imitation</p>
      <p>unfortunately they are terrible and blurry</p>
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
      outfitView: {
        coatsView: `` , 
        topsView: `` , 
        bottomsView: `` , 
        shoesView: `` , 
        accessoriesView: `` , 
      } , 
      
      coats: [
       {
        coatName: 'Baseball Shirt - Black',
        coatImage:'https://static.wikia.nocookie.net/lovenikki/images/f/f0/Baseball_Shirt-Black.png'
      },
       {
        coatName: 'Gray Plaid Coat',
        coatImage:'https://static.wikia.nocookie.net/lovenikki/images/4/41/Gray_Plaid_Coat.png',
      }, {
        coatName: 'Pink Cardigan',
        coatImage: 'https://static.wikia.nocookie.net/lovenikki/images/8/80/Little_Secretary.png',
      },
       {
        coatName: 'Sweater Vest',
        coatImage: 'https://static.wikia.nocookie.net/lovenikki/images/7/76/Sweater_Vest.png',
      },
      ],

      tops: [
       {
        topName: 'Blouse - Pink',
        topImage:'https://static.wikia.nocookie.net/lovenikki/images/0/0f/Sweet_Jasmine%C2%B7Pink.png'
      },
       {
        topName: 'Sweater - Peach and Green',
        topImage:'https://static.wikia.nocookie.net/lovenikki/images/f/fa/Autumn_Sweet-Green.png',
      }, {
        topName: 'Tank Top - Black',
        topImage: 'https://static.wikia.nocookie.net/lovenikki/images/7/72/Tank_Top-Black.png',
      }],
      bottoms: [
       {
        bottomName: 'Shorts - Blue',
        bottomImage:'https://static.wikia.nocookie.net/lovenikki/images/3/36/Casual_Shorts-Blue.png'
      },
       {
        bottomName: 'Skirt - Red',
        bottomImage:'https://static.wikia.nocookie.net/lovenikki/images/5/56/Classic_Kilt-Red.png',
      }, {
        bottomName: 'Pants - Black',
        bottomImage: 'https://static.wikia.nocookie.net/lovenikki/images/b/bc/Gentle_Waiter-Trousers.png',
      }],

      shoes: [
       {
        shoeName: 'Sandals - Purple',
        shoeImage:'https://static.wikia.nocookie.net/lovenikki/images/1/1b/Purple_Cloth_Sandals.png'
      },
       {
        shoeName: 'Hiking Boots',
        shoeImage:'https://static.wikia.nocookie.net/lovenikki/images/7/7d/Nipped_Boots-Black.png',
      }, {
        shoeName: 'Sneakers - Black',
        shoeImage: 'https://static.wikia.nocookie.net/lovenikki/images/f/fa/Ordinary_Canvas_Shoes.png',
      }],

      accessories: [
       {
        accessoryName: 'Floral Hairband - Pink',
        accessoryImage:'https://static.wikia.nocookie.net/lovenikki/images/3/3c/Floral_Hairband-Pink.png'
      },
       {
        accessoryName: 'Leather Gloves',
        accessoryImage:'https://static.wikia.nocookie.net/lovenikki/images/f/ff/Leather_Gloves.png',
      }, {
        accessoryName: 'Galaxy Earrings',
        accessoryImage: 'https://static.wikia.nocookie.net/lovenikki/images/3/3e/Galaxy_Earrings.png',
      }],
    }
  },
  methods: {
    showCoats(el) {
      console.log(el)
      if(el!==true ) {
        this.display.coatsDisplay = true
        this.display.topsDisplay = false
        this.display.bottomsDisplay = false
        this.display.shoesDisplay = false
        this.display.accessoriesDisplay = false

      } else {
        this.display.coatsDisplay = false
      }
    },
    // opens one category at a time to not clutter the screen
    // also closes the category again if the header is clicked a second time
    // i feel like there's a better way to do this but oh well
    showTops(el) {
      console.log(el)
      if(el!==true ) {
        this.display.coatsDisplay = false
        this.display.topsDisplay = true
        this.display.bottomsDisplay = false
        this.display.shoesDisplay = false
        this.display.accessoriesDisplay = false

      } else {
        this.display.topsDisplay = false
      }
    },
    showBottoms(el) {
      console.log(el)
      if(el!==true ) {
        this.display.coatsDisplay = false
        this.display.topsDisplay = false
        this.display.bottomsDisplay = true
        this.display.shoesDisplay = false
        this.display.accessoriesDisplay = false

      } else {
        this.display.bottomsDisplay = false
      }
    },
    showShoes(el) {
      console.log(el)
      if(el!==true ) {
        this.display.coatsDisplay = false
        this.display.topsDisplay = false
        this.display.bottomsDisplay = false
        this.display.shoesDisplay = true
        this.display.accessoriesDisplay = false

      } else {
        this.display.shoesDisplay = false
      }
    },
    showAccessories(el) {
      console.log(el)
      if(el!==true ) {
        this.display.coatsDisplay = false
        this.display.topsDisplay = false
        this.display.bottomsDisplay = false
        this.display.shoesDisplay = false
        this.display.accessoriesDisplay = true

      } else {
        this.display.accessoriesDisplay = false
      }
    },

    displayCoatView(coatImage) {
      console.log(this.outfitView.coatsView)
      if (this.outfitView.coatsView === coatImage) {
        this.outfitView.coatsView= ``
      } else {
        this.outfitView.coatsView = coatImage
      }
    },
    // selects/deselects clothes
    // i also feel like theres a better way to do this 
    // its all just the same code but the names are changed
    displayTopView(topImage) {
      console.log(this.outfitView.topsView)
      if (this.outfitView.topsView === topImage) {
        this.outfitView.topsView= ``
      } else {
        this.outfitView.topsView = topImage
      }
    },
    displayBottomView(bottomImage) {
      console.log(this.outfitView.bottomsView)
      if (this.outfitView.bottomsView === bottomImage) {
        this.outfitView.bottomsView= ``
      } else {
        this.outfitView.bottomsView = bottomImage
      }
    },
    displayShoeView(shoeImage) {
      console.log(this.outfitView.shoesView)
      if (this.outfitView.shoesView === shoeImage) {
        this.outfitView.shoesView= ``
      } else {
        this.outfitView.shoesView = shoeImage
      }
    },
    displayAccessoryView(accessoryImage) {
      console.log(this.outfitView.accessoriesView)
      if (this.outfitView.accessoriesView === accessoryImage) {
        this.outfitView.accessoriesView= ``
      } else {
        this.outfitView.accessoriesView = accessoryImage
      }
      // wanted to have several individual accessories displayed
      // while still having the ability to select/deselect them individually but idk how
    },
    // its too late to have a dress categroy that gets rid of the top and bottom categories when its selected right
    // mostly bc im too out of it rn to figure it out by actually thinking
  }
  // i wanted to have a saved outfit function but again i cant think rn
  // this is not aesthetically pleasing

  /* components: {
    HelloWorld
  } */
}
</script>

<style lang="scss">
.fixed {
  position: absolute;
  display: flex;
  height: 10rem;
  width: 8rem;
  justify-content: center;
  text-align: center;
  align-items: center;
  z-index: 1;
}
ul {
  list-style: none;
  margin: 0 auto;
  padding: 0;
}
img {
  z-index: 2;
}
.items img {
  width: 60%;
  z-index: 2;
}
.accessories-view img {
  width: 8rem;
  height: auto;
}
.outfit-view {
  display: flex;
  flex-direction: column;
  width: 65%;
  height: 90vh;
  flex-wrap: wrap;
  background-color: #C89595;
  border-radius: 1rem;
  padding-top: 2rem;

}
.view {
  display: flex;
  flex-grow: 1;
  justify-content: center;
  align-items: center;
  margin: 0 auto;
  text-align: center;
}
.view-img {
  height: 11rem;
}

.clothes-view {
  display: flex;
  flex-direction: column;
  width: 30%;
  background-color: #DDBEBE;
  border-radius: 1rem;
}
.category {
  background-color: #C37B89;
  border-radius: .75rem;
  width: 60%;
  padding: .5rem 0rem;
  justify-content: center;
  align-items: center;
  margin: .75rem auto;
  text-align: center;
  box-shadow: .15rem .2rem .5rem #888;
  
}
.category-title {
  font-size: 1.25rem;
  border-bottom: .2rem solid black;
  width: 75%;
  text-align: center;
  align-items: center;
  justify-content: center;
  margin: .5rem auto;
}
html, body {
  background-color: #EDEDED;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-content: center;
  color: #2c3e50;
  margin: auto;
}
</style>
