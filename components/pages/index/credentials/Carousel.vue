<template>
  <div>
    <VueSlickCarousel v-bind="carouselSettings">
      <div v-for="(credential, index) in prop" :key="index">
        <Credential :prop="credential" />
      </div>
    </VueSlickCarousel>
  </div>
</template>
<script>
import Credential from "./Credential";
export default {
  props: ["prop"],
  components: {
    Credential
  },
  data() {
    return {
      carouselSettings: {
        slidesToShow: 3,
        infinite: false,
        slidesToScroll: 1,
        responsive: [
          {
            breakpoint: 1024,
            settings: {
              slidesToShow: 3,
              slidesToScroll: 3,
              infinite: true,
              dots: true
            }
          },
          {
            breakpoint: 768,
            settings: {
              slidesToShow: 2,
              slidesToScroll: 2,
              initialSlide: 2
            }
          },
          {
            breakpoint: 480,
            settings: {
              slidesToShow: 1,
              slidesToScroll: 1
            }
          }
        ]
      }
    };
  }
};
</script>
<!-- This css is for carousel only. if I will add scoped it won't work -->
<style>
.slick-arrow {
  background: #acacac;
  font-weight: 900 !important;
  border-radius: 50%;
}
.slick-prev:hover,
.slick-prev:focus,
.slick-next:hover,
.slick-next:focus {
  background: #acacac;
}
.slick-next,
.slick-prev {
  padding-top: 1px !important;
}
</style>