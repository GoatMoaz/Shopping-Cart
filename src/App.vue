<template>
  <Nav :cartItems="cartItems" @hideCart="toggleCart" />
  <Cards @addToCart="handleAddToCart" :hideCart="hideCart" />
  <Cart :cartItems="cartItems" @closeCart="handleCloseCart" v-if="hideCart" />
</template>

<script>
import Cards from "./components/Cards.vue";
import Nav from "./components/Nav.vue";
import Cart from "./components/Cart.vue";

export default {
  name: "App",
  components: {
    Cards,
    Nav,
    Cart,
  },
  data() {
    return {
      cartItems: [],
      hideCart: false,
    };
  },
  methods: {
    handleAddToCart(card) {
      this.cartItems.push(card);
    },
    handleCloseCart() {
      this.hideCart = false;
    },
    toggleCart() {
      this.hideCart = !this.hideCart;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #eaeff3;
  text-align: center;
  margin: 0;
  padding: 0;
}
</style>
