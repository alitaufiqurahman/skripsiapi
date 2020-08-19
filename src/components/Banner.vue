<template>
  <!-- Banner Carousel -->
  <section class="hero-section" style="margin-top: -4vh">
    <carousel
      class="hero-items"
      :items="1"
      :nav="false"
      :loop="true"
      :autoplay="true"
      :dots="false"
      :autoplaySpeed="true"
    >
      <div class="single-hero-items set-bg" style="background-image: url('/img/q1@2x.png')">
        <div class="container">
          <div class="row">
            <div class="col-lg-5">
              <span style="color: #000000;">Bag</span>
              <h1>Ransel Holic</h1>
              <p style="color: #000000;">
                Spunbond adalah bahan kain yang digunakan untuk mengganti bahan
                plastik digunakan untuk kesehatan, dan bahan ini bersifat ramah
                lingkungan
              </p>
              <a href="#shop" class="primary-btn">Shop Now</a>
            </div>
          </div>
        </div>
      </div>
      <div class="single-hero-items set-bg" style="background-image: url('/img/q9@2x.png')">
        <div class="container">
          <div class="row">
            <div class="col-lg-5">
              <span style="color: #000000;">Bag</span>
              <h1>Shoes Holic</h1>
              <p style="color: #000000;">
                Tas khusus untuk menyimpan sepatu bola berbahan spunbound yang
                ramah lingkungan dengan bahan yang mudah terurai
              </p>
              <a href="#shop" class="primary-btn">Shop Now</a>
            </div>
          </div>
        </div>
      </div>
    </carousel>

    <div class="single-hero-items set-bg" id="shop">
      <div class="container">
        <div class="row">
          <div class="col-lg-12 text-center">
            <h2 style="font-weight: 800; letter-spacing: 1.5px;;">SHOP STYLES BY FAT</h2>
          </div>
        </div>
      </div>
    </div>
  </section>
  <!-- Banner Carousel End -->
</template>

<script>
import carousel from "vue-owl-carousel";

export default {
  name: "Banner",
  components: {
    carousel
  }
};
</script>
