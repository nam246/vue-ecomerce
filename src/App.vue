<template>
  <div class="container">
    <Header :product='product' :cart="cart"/>
    <hr>
    <Main :product='product' @add-to-cart="addToCart(product.quantity)"/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Main from './components/Main.vue'

export default {
  name: 'App',
  data() {
    return {
      cart: [],
      product: {
        name: 'men shoes',
        quantity: 0,
        price: 250,
        discount: 50,
      },
    }
  },
  components: {
    Header,
    Main
  },
  methods: {
    addToCart(product) {
      if(this.product.quantity > 0) {
        // console.log(product)
        this.cart.push(product)
        console.log(this.cart)
      }
    }
  }
}
</script>

<style>
*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Kumbh Sans', sans-serif;
}

:root {
    /* Primary */
    --orange: hsl(26, 100%, 55%);
    --pale-orange: hsl(25, 100%, 94%);
    /* Neutral */
    --very-vark-blue: hsl(220, 13%, 13%);
    --dark-grayish-blue: hsl(219, 9%, 45%);
    --grayish-blue: hsl(220, 14%, 75%);
    --light-grayish-blue: hsl(223, 64%, 98%);
    --white: hsl(0, 0%, 100%);
    /* (with 75% opacity for lightbox background) */
    --black: hsl(0, 0%, 0%);
}

.container {
    width: 80%;
    margin: 0 auto;
    padding-top: 1.2rem;
}

</style>
