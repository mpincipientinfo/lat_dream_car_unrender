<template>
  <div>
    <div class="background_image" :style="{ backgroundImage: `url(${prop.background_image.url})` }">
      <div class="d-flex flex-column align-items-center justify-content-center h-100 pt-40">
        <b-img :src="prop.image.url"></b-img>
        <h1 class="text-light title">
          <i>
            {{ prop.title }}
          </i>
        </h1>
        <h2 class="subtitle text-light">
          {{ prop.subtitle }}
        </h2>
        <b-row class="w-100 pt-40">
          <b-col lg="6" md="12" class="justify-content-lg-end justify-content-center d-flex">
            <ButtonDanger :prop="{ text: prop.button_1, path: '#', addBtnClass: 'text-uppercase' }" />
          </b-col>
          <b-col lg="6" md="12" class="justify-content-lg-start justify-content-center d-md-flex d-none">
            <ButtonInfoDark :prop="{ text: prop.button_2, path: '#', addBtnClass: 'text-uppercase' }" />
          </b-col>
        </b-row>
      </div>
    </div>
  </div>
</template>
<script>
import button from "@/components/common/button/index.js";
export default {
  props: ["prop"],
  components: {
    ButtonDanger: button.ButtonDanger,
    ButtonInfoDark: button.ButtonInfoDark
  }
};
</script>
<style scoped>
.justify-content-lg-start {
  padding-left: 5px;
}
.justify-content-lg-end {
  padding-right: 25px;
}
.pt-40 {
  padding-top: 40px !important;
}
.background_image {
  height: 800px;
}
.title {
  font-family: Open Sans, sans-serif !important;
  font-size: 2.3125rem;
  padding-top: 27px;
  letter-spacing: 1px;
}
.subtitle {
  font-family: Open Sans, sans-serif !important;
  font-size: 1.0625rem;
}
</style>
