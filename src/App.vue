<template>
  <div class="container">
      <div class="products">
        <product v-for="product in products" v-bind:product="product"></product>
      </div>
      <div class="shopping-cart">
        <shopping-cart></shopping-cart>
      </div>
  </div>
</template>

<script>
import ShoppingCart from './components/ShoppingCart.vue'
import Product from './components/Product.vue'

export default {
  created () {
    // fetch data from server
    // i m using dummy data for now..
    var dummy = [
      {id: 1, title: '商品 1', price: 40, image: 'logo.png'},
      {id: 2, title: '商品 2', price: 90, image: 'logo.png'},
      {id: 3, title: '商品 3', price: 10, image: 'logo.png'},
      {id: 4, title: '商品 4', price: 20, image: 'logo.png'}
    ]

    this.products = dummy
  },
  data () {
    return {
      products: []
    }
  },
  components: { Product, ShoppingCart }
}
</script>

<style>
  * {
    box-sizing: border-box;
  }

  body {
    font-family: Helvetica, sans-serif;
    margin: 0;
  }

  .container {
    width: 100%;
    color: #4C5263;
    width: 100%;
    padding: 2em;
  }

  .products {
    width: 75%;
    float: left;
  }

  .shopping-cart {
    width: 25%;
    float: left;
  }
</style>
