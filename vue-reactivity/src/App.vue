<template>
  <div id="app">
    <div class="outfit-view">
      <div class="view coat-view">coat</div>
      <div class="view tops-view">tops</div>
      <div class="view bottoms-view">bottoms</div>
      <div class="view shoes-view">shoes</div>
      <div class="view accessories-view">accessories</div>
    </div>
    <div class="clothes-view">
      <div class="category coat">
        <p>Coat</p>
        <ul>
          <li v-for="coat in coats" :key="coat.coatName" >
           
            <img :src="coat.coatImage" alt=""></li>
        </ul>
      </div>
      <div class="category tops">Tops</div>
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
      coats: [{
        coatName: 'coat1',
        coatImage:'https://www.vuemastery.com/images/challenges/vmSocks-green-onWhite.jpg'
      },
       {
        coatName: 'coat2',
        coatImage:'https://www.vuemastery.com/images/challenges/vmSocks-green-onWhite.jpg',
      }, {
        coatName: 'coat3',
        coatImage: 'https://www.vuemastery.com/images/challenges/vmSocks-green-onWhite.jpg',
      }],
    }
  }
  /* components: {
    HelloWorld
  } */
}
</script>

<style lang="scss">
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
  display: flex;
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
