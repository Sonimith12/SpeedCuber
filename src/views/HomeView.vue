<template>
  <div class="picture">
    <img src="../../image/a.jpeg" alt="">
  </div>  
  <div class="text_one">Boost your performance, break the record and get the rewards !</div>
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
  <div class="text_two">
    Best Selling Product
  </div>
  <div class="product_container_one">
    <div class="product">
      <img src="../../image/product.png" alt="">
    </div>
    <div class="product">
      <img src="../../image/product.png" alt="">
    </div>
    <div class="product">
      <img src="../../image/product.png" alt="">
    </div>
    <div class="product">
      <img src="../../image/product.png" alt="">
    </div>
  </div>

  <div class="product_container_two">
    <div class="product">
      <img src="../../image/product.png" alt="">
    </div>
    <div class="product">
      <img src="../../image/product.png" alt="">
    </div>
    <div class="product">
      <img src="../../image/product.png" alt="">
    </div>
    <div class="product">
      <img src="../../image/product.png" alt="">
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
        <div>
          Stay in touch !
        </div>
        <input type="email">
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
}
.product_container_two {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 30px;
  padding-top: 25px;
  padding-bottom: 100px;
}
.product {
  border: solid 1px;
  width: 280px;
  height: 227px;
  display: flex;
}
</style>
