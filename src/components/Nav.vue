<template>
  <nav class="nav">
    <div class="container">
      <div class="nav-header">
        <div class="nav-title">Shopping Cart</div>
        <div
          class="cart-icon"
          @click="(hideCart = !hideCart), $emit('hideCart')"
        >
          <svg
            xmlns="http://www.w3.org/2000/svg"
            width="24"
            height="24"
            viewBox="0 0 24 24"
            fill="none"
            stroke="currentColor"
            stroke-width="2"
            stroke-linecap="round"
            stroke-linejoin="round"
            class="feather feather-shopping-cart"
          >
            <circle cx="9" cy="21" r="1"></circle>
            <circle cx="20" cy="21" r="1"></circle>
            <path
              d="M1 1h4l2.68 13.39a2 2 0 0 0 2 1.61h10.72a2 2 0 0 0 2-1.61L23 6H6"
            ></path>
          </svg>
          <div v-if="cartItems.length" class="counter">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              width="16"
              height="16"
              viewBox="0 0 24 24"
              fill="#ff0000"
              stroke="currentColor"
              stroke-width="2"
              stroke-linecap="round"
              stroke-linejoin="round"
              class="feather feather-circle"
            >
              <text x="50%" y="50%" text-anchor="middle" dy=".3em">
                {{ cartItems.length }}
              </text>
            </svg>
          </div>
        </div>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  props: ["cartItems", "hideCart"],
  name: "Nav",
};
</script>

<style>
.nav {
  background-color: rgb(245, 217, 217);
  color: #495057;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  padding: 0.5rem 1rem;
  margin-bottom: 20px;
}
.nav-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.nav-title {
  font-size: 1.25rem;
  font-weight: bold;
}
.container {
  max-width: 1200px;
  margin: 0 auto;
}
.cart-icon {
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
}
.cart-icon svg .counter {
  margin-right: 10px;
}
.cart-icon svg:hover,
.counter:hover {
  cursor: pointer;
}
.counter {
  position: absolute;
  top: -5px;
  right: -5px;
  width: 16px;
  height: 16px;
  border-radius: 50%;
  background-color: #ff0000;
  color: #fff;
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>