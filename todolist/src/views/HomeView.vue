<template>
  <div class="home">
    <carousel class="carousel" v-slot="{ currentSlide }">
      <slide  v-for="(slide, index) in carouselSlides" :key="index">
        <div v-show="currentSlide === index + 1" class="slide-info">
          <img :src="slide" alt="">
        </div>
      </slide>
    </carousel>
  </div>
</template>

<script>
// @ is an alias to /src
import carousel from "@/components/carousel";
import slide from "@/components/slide";

export default {
  name: 'HomeView',
  components: {
    carousel,
    slide
  },
  setup(){
    const carouselSlides = ["../assets/1.jpg", "../assets/2.jpg", "../assets/3.jpg"];

    return{
      carouselSlides
    }
  }
}
</script>

<style>
  .carousel{
    position: relative;
    max-height: 50%;
    height: 50%;
  }
  .slide-info{
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    max-height: 100%;
    height: 100%;
    min-width: 100%;
    object-fit: cover;
  }

</style>