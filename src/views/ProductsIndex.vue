<script>
import axios from 'axios'
export default {
  data: function () {
    return {
      message: "Welcome to all products",
      products: []
    };
  },
  created: function () {
    this.indexProducts()
  },
  methods: {
    indexProducts: function () {
      console.log('all products')
      axios.get("/products".json).then(response => {
        console.log(response.data)
        this.products = response.data
      })
    }
  },
};
</script>

<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <h3>All products: </h3>
    <div v-for="product in products" v-bind:key="product.id">
      <p>{{ product.name }}</p>

    </div>
  </div>
</template>

<style>
</style>