<template>
  <div class="cart">
    <div class="cart-content">
      <div class="cart-header">
        <h2>Cart</h2>
        <button @click="$emit('closeCart')">X</button>
      </div>
      <div class="cart-items" v-if="cartItems.length">
        <div
          v-for="item in cartItems"
          :key="item.title"
          style="border-bottom: 1px solid white; margin: 5px"
        >
          <img :src="item.img" alt="item.title" />
          <p>{{ item.title }}</p>
          <p>{{ item.price }}$</p>
        </div>
        <button class="checkout">Check out</button>
      </div>
      <p v-else>No items in the cart</p>
    </div>
  </div>
</template>

<script>
export default {
  props: ["cartItems"],
  name: "Cart",
  data() {
    return {
      isCartOpen: false,
    };
  },
};
</script>

<style>
.cart {
  display: flex;
  justify-content: center;
  align-items: center;
  position: fixed;
  top: 0;
  right: 0;
  width: 300px;
  height: 100%;
  z-index: 100;
}

.cart-content {
  background: rgb(0, 0, 0, 0.5);
  width: 100%;
  height: 100%;
  padding: 1rem;
  overflow-y: auto;
  max-height: 100%;
}

.cart-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 1rem;
}

.cart-header button {
  background: none;
  border: none;
  font-size: 1.5rem;
  cursor: pointer;
  transition: 0.3s ease;
  color: white;
}

.cart-header button:hover {
  color: red;
}

.cart-items {
  display: flex;
  flex-direction: column;
}

p {
  display: inline-block;
  margin: 5px;
}

img {
  width: 200px;
  height: 200px;
  object-fit: cover;
}

.checkout {
  background: #3697f7;
  color: white;
  border: none;
  border-radius: 10px;
  padding: 0.5rem 1rem;
  margin-top: 1rem;
  cursor: pointer;
}
</style>