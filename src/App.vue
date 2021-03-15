<template>
  <div id="app">
    <carousel>
      <carousel-slide v-for="n in slides" :index="n-1">
        <div class="slide">Slide {{ n }}</div>
        <img :src="'https://picsum.photos/630/300?random='+n">
      </carousel-slide>
    </carousel>
    <button @click="addSlide">Add slide</button>
    <button @click="removeSlide">Remove slide</button>
    <todos></todos>
  </div>
</template>

<script>
import Todos from './components/Todos'
import Carousel from "./components/carousel/Carousel";
import CarouselSlide from "./components/carousel/CarouselSlide";

export default {
  name: 'App',
  components: {
    CarouselSlide,
    Todos,
    Carousel
  },
  data() {
    return {
      slides: 5
    }
  },
  methods: {
    addSlide() {
      this.slides++
    },
    removeSlide() {
      this.slides--
    }
  }
}
</script>

<style>
  .slide{
    position: absolute;
    left: 0;
    right: 0;
    text-align: center;
    top: 50%;
    color: #FFF;
    font-size: 16px;
  }
</style>
