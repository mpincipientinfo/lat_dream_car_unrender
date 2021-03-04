<template>
  <b-container class="py-5 my-5">
    <div class="d-flex flex-column align-items-center justify-content-center h-100">
      <h1 class="title">{{ prop.title }}</h1>
      <p class="subtitle my-55 pb-4 pt-3 mt-2 mb-3">{{ prop.subtitle }}</p>
    </div>
    <Carousel :prop="prop.referenzen" />
  </b-container>
</template>
<script>
import Carousel from "./Carousel";
export default {
  props: ["prop"],
  components: {
    Carousel
  }
};
</script>
<style scoped>
.my-55 {
  margin-right: 55px;
  margin-left: 55px;
}
.title {
  font-family: Lora, serif !important;
  font-size: 2.625rem;
  font-weight: 500;
  color: #182540;
}
.subtitle {
  font-family: Open Sans, sans-serif !important;
  font-size: 1.0625rem;
  font-weight: 600;
  color: #182540;
  text-align: center;
}
</style>
