<template>
  <div>
    <div class="picture">
      <transition name="slide">
        <img :key="currentImage" :src="currentImage" alt="image">
      </transition>
    </div>  
    <div class="text_one">Boost your performance, break the record and get the rewards!</div>
    <div class="type_cube">
      <div class="type">
        <img src="../../image/image 47.png" alt="">
      </div>
      <div class="type">
        <img src="../../image/image 47 (1).png" alt="">
      </div>
      <div class="type">
        <img src="../../image/image 47 (2).png" alt="">
      </div>
      <div class="type">
        <img src="../../image/image 26.png" alt="">
      </div>
      <div class="type">
        <img src="../../image/image 47 (3).png" alt="">
      </div>
    </div>
    <div class="text_two">Best Selling Product</div>
    <div class="product_container_one">
      <div class="product" v-for="product in products" :key="product.id">
        <div class="product_image">
          <img :src="product.image" alt="Product Image">
        </div>
        <div class="product_details">
          <div class="product_name">{{ product.product_name }}</div>
          <div class="product_price">{{ product.price }}</div>
          <div class="product_description">{{ product.description }}</div>
        </div>
      </div>
    </div>
    
    
    <div class="footer">
      <div class="bottom_logo">SpeedCuber <b>by Kai</b></div>
      <div class="brand_container">
        <div class="brand">
          <img src="../../image/brand1.png" alt="">
        </div>
        <div class="brand">
          <img src="../../image/brand2.png" alt="">
        </div>
        <div class="brand">
          <img src="../../image/brand3.png" alt="">
        </div>
        <div class="brand_diff">
          <img src="../../image/brand4.png" alt="">
        </div>
      </div>
      <div class="filling_email">
        <div>Stay in touch!</div>
        <input class="email" type="email" placeholder="email">
      </div>
    </div>
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .home {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}

.brand_container{
  display: flex;
  gap: 45px; 
  align-items: center;
}
.brand {
  width: 80px;
  height: 80px;

}
.brand_diff {
  width: 160px;
  height: 80px;
  display: flex;
  align-self: center;

}
.bottom_logo {
  margin-left: 20px;
}
.footer {
  display: flex;
  justify-content: space-between;
  height: 100px;
  background-color: lightgray;
  align-items: center;
}

.picture{
  display: flex;
  justify-content: center;
}
.picture img{
  padding-top: 20px;
  width: 1200px;
  height: 572px;
}
.text_one {
  font-size: 25px;
  font-family: monospace;
  padding-top: 20px;
  display: flex;
  justify-content: center;
}
.type {
  border: solid 1px;
  width: 217px;
  height: 210px;
  display: flex;
  justify-content: center;
}
.text_two {
  font-size: 25px;
  font-family: monospace;
  padding-top: 25px;
  display: flex;
  justify-content: center;
}
.type_cube {
  padding-top: 25px;
  display: flex;
  justify-content: center;
  gap: 30px;
}
.product_container_one {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 30px;
  padding-top: 25px;
  align-items: center; /* Align items vertically in the center */
}
.product_container_two {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 30px;
  padding-top: 25px;
  padding-bottom: 100px;
  align-items: center; /* Align items vertically in the center */
}
.product {
  border: solid 1px;
  width: 280px;
  height: 250px;
  display: flex;
  align-items: center; /* Align items vertically in the middle */
}
.product_image {
  flex-grow: 1;
}

.product_image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.product_details {
  display: flex;
  flex-direction: column;
  justify-content: center; /* Align details vertically in the middle */
}

.product_name {
  font-size: 16px;
  font-weight: bold;
  margin-bottom: 5px;
}

.product_price {
  font-size: 14px;
  color: #888;
}

.product_description {
  font-size: 14px;
  color: #555;
}
.email {
  border: solid 2px;
  padding-left: 10px;
  margin-right: 20px;
}
.picture {
  position: relative;
}
.slide-enter-active, .slide-leave-active {
  animation: slide-in 0.5s ease;
}
.slide-enter, .slide-leave-to {
  transform: translateX(100%);
  position: absolute;
}
@keyframes slide-in {
  0% {
    transform: translateX(100%);
  }
  100% {
    transform: translateX(0);
  }
}
</style>


<script>
import axios from 'axios';

export default {
  data() {
    return {
      images: [
        "../../image/a.jpeg",
        "../../image/b.jpeg",
        "../../image/c.jpeg"
      ],
      currentImageIndex: 0,
      products: []
    };
  },
  mounted() {
    setInterval(this.changeImage, 5000);
    this.fetchProduct();
  },
  methods: {
    changeImage() {
      this.currentImageIndex = (this.currentImageIndex + 1) % this.images.length;
    },
    async fetchProduct() {
      try {
        const response = await axios.get('http://localhost:3000/products');
        this.products = response.data;
      } catch (error) {
        console.error(error);
      }
    }
  },
  computed: {
    currentImage() {
      return this.images[this.currentImageIndex];
    }
  }
};
</script>