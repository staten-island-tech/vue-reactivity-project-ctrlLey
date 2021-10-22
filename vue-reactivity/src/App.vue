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
      <div class="category coat">Coat</div>
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
      // coats: [coat1, coat2, coat3],
    }
  }
  /* components: {
    HelloWorld
  } */
}
</script>

<style lang="scss">
.outfit-view {
  display: flex;
  flex-direction: column;
  width: 65%;
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
