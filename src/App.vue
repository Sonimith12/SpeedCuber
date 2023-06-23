<template>
  <div class="wrapper">
    <nav class="p-5">
      <div class="logo">
        <img src="../image/logo.png" alt="">
      </div>
      <div class="nav flex gap-x-3">

        <div class="search-container">
          <input type="text" placeholder="Search..." name="search">
          <button type="submit" class="search-button">
            <img src="../image/search.png" alt="Search Icon" class="search-icon">
          </button>
        </div>
        
        <RouterLink to="/" class="nav-link">Home</RouterLink>
        <RouterLink to="/about" class="nav-link">About</RouterLink>
        <RouterLink to="/product" class="nav-link">Product</RouterLink>
        <RouterLink to="/login" class="nav-link">Login</RouterLink>

        <!-- <button @click="$emit('checkout')">Go to checkout</button> -->

      </div>
    </nav>
  </div>
  <!-- <div>
    <Checkout @cancel="isCheckingOut = false" v-if="isCheckingOut" />
    <RouterView v-else @checkout="isCheckingOut = true" />
  </div> -->

  <router-view />
  
</template>

<script>
import { RouterLink, RouterView } from "vue-router";
import Index from "./views/Index.vue";
import Checkout from "./views/Checkout.vue";
export default {
  data() {
    return {
      isCheckingOut: false,
    };
  },
  components: {
    Index,
    Checkout,
  },
};
</script>

<style scoped>
.wrapper {
  width: 100%;
  margin: 0 auto;
}

.logo {
  margin-left: 20px;
  margin: 0 auto 2rem;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

.search-container {
  display: flex;
  align-items: center;
}

.search-container input {
  margin-right: 0.5rem;
}

.nav {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  margin-top: 1rem;
}

.nav-link {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

.nav-link:first-child {
  border-left: none;
}

@media (min-width: 1024px) {
  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;
    padding: 1rem 0;
    margin-top: 1rem;
  }
}
</style>
