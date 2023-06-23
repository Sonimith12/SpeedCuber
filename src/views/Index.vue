<template>
  <!-- <header>
    <div class="wrapper">
      <nav class="p-5">
        <div class="logo">
          <img src="../../image/logo.png" alt="">
        </div>
        <div class="nav flex gap-x-3">

          <div class="search-container">
            <input type="text" placeholder="Search..." name="search">
            <button type="submit" class="search-button">
              <img src="../../image/search.png" alt="Search Icon" class="search-icon">
            </button>
          </div>
          
          <RouterLink to="/">Home</RouterLink>
          <RouterLink to="/about">About</RouterLink>
          <RouterLink to="/product">Product</RouterLink>
          <RouterLink to="/login">Login</RouterLink> -->

          <!-- <button @click="$emit('checkout')">Go to checkout</button> -->
          
        <!-- </div>
      </nav>
    </div>
  </header>
  <RouterView /> -->
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

  .search-container {
    display: flex;
    justify-content: center;
    height: 40px;
  }
  
  input[type=text] {
    padding: 6px;
    border-radius: 5px 0 0 5px;
    width: 60%;
  }
  
  .search-button {
    background-color: #f44336;
    color: #fff;
    border: none;
    border-radius: 0 5px 5px 0;
    padding: 10px 20px;
    cursor: pointer;
    
  }
  
  .search-icon {
    height: 20px;
    width: 20px;
    
  }
</style>
