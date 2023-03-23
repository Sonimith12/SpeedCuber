<template>
  <header>
    <div class="wrapper">
      <nav class="p-5">
        <div class="logo">
          <img src="../../image/logo.png" alt="">
        </div>
        <div class="nav flex gap-x-3">
          <input class="search" type="text" placeholder="search">
          <RouterLink to="/">Home</RouterLink>
          <RouterLink to="/about">About</RouterLink>
          <RouterLink to="/product">Product</RouterLink>
          <!-- <button @click="$emit('checkout')">Go to checkout</button> -->
        </div>
      </nav>
    </div>
  </header>
  <RouterView />
</template>

<style>
  nav{
    display: flex;
    justify-content: space-between;
  }
  .logo {
    justify-content: start;
  }
  .wrapper {
    background-color:lightgray;
    height: 85px;
    align-items: center;
  }
  .search {
    height: 35px;
    border: solid 2px;
  }
  
  
</style>
