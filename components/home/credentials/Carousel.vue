<template>
  <div>
    <VueSlickCarousel v-bind="carouselSettings">
      <div>1</div>
      <div>2</div>
      <div>3</div>
      <div>4</div>
      <div>4</div>
      <div>4</div>
      <div>4</div>
      <div>4</div>
    </VueSlickCarousel>
  </div>
</template>
<script>
export default {
  props: ["prop"],
  data() {
    return {
      carouselSettings: {
        slidesToShow: 3,
        infinite: false,
        slidesToScroll: 1
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