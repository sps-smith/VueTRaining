<template>
      <product-list :products="theProducts" title="Shop our award-winning product line"></product-list>
</template>

<script>
import ProductList from "./ProductList.vue";

export default {
  name: 'app',
  data() {
    return{
      theProducts: []
    };
  },
  components: {
    "product-list": ProductList
  },
  created: function() {
      $.getJSON('https://hplussport.com/api/products')
          .done( data => {this.theProducts = data
               
          });
  }
}
</script>

<style scoped>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
