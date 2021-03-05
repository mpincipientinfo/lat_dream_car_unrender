<template>
  <div class="background_image" :style="{ backgroundImage: `url(${prop.background_image.url})` }">
    <b-container class="bv-example-row d-flex flex-column align-items-left pt-5 h-100 container">
      <div class="text-sm-left text-center mt-5 pt-5">
        <h2 class="text-light title mb-3 mt-3">
          {{ prop.title }}
        </h2>
        <div>
          <ButtonDangerExpand :prop="{ text: prop.button, path: '#' }" />
        </div>
      </div>
    </b-container>
  </div>
</template>
<script>
import button from "@/components/common/button";
export default {
  props: ["prop"],
  components: {
    ButtonDangerExpand: button.ButtonDangerExpand
  }
};
</script>
<style scoped>
.background_image {
  background-repeat: no-repeat;
  background-size: cover;
  background-position: 50%;
  box-shadow: inset 0 0 0 2000px rgba(17, 17, 17, 0.4);
  width: 100%;
  height: 600px;
}
.title {
  font-family: Lora, serif !important;
  font-size: 2.625rem;
}
</style>
