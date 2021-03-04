<template>
  <b-row class="m-0">
    <!-- For first record: display image in right, for second record: display image in left & continue same pattern -->
    <!-- image in right -->
    <b-col lg="6" class="d-none d-md-block p-0" v-if="count % 2 != 0">
      <img :src="prop.image.url" class="w-100 fluid image h-100" />
    </b-col>
    <b-col lg="6" sm="12" class="p-0 custom_padding pt-5 col-sm-12 col-lg-6" style="position: relative">
      <h2 class="pb-3 title">{{ prop.title }}</h2>
      <div v-for="(list, index) in prop.list" :key="index">
        <b-img src="@/assets/images/tick.e546d3c.svg" class="float-left"> </b-img>
        <p class="list_title pb-3 ml-2">{{ list.title }}</p>
      </div>
      <div class="mb-2 pt-24 d-flex flex-sm-row justify-content-center justify-content-sm-start flex-column w-100">
        <div class="w-50">
          <ButtonDangerExpand :prop="{ text: prop.button, path: '#' }" />
        </div>
        <div class="d-flex align-items-start flex-column" v-if="prop.price">
          <div>
            <div class="price_tag">
              <b-img src="@/assets/images/price_tag.jpeg"></b-img>
              <p class="price_tag_text">PRIES</p>
            </div>
            <h5 class="price">
              {{ prop.price }}
            </h5>
          </div>
        </div>
      </div>
    </b-col>
    <!-- image in left -->
    <b-col lg="6" class="d-none d-md-block p-0 h-652" v-if="count % 2 == 0">
      <img :src="prop.image.url" class="w-100 fluid h-100" />
    </b-col>
  </b-row>
</template>
<script>
import button from "@/components/common/button";
export default {
  props: ["count", "prop"],
  components: { ButtonDangerExpand: button.ButtonDangerExpand }
};
</script>
<style scoped>
.custom_padding {
  padding-top: 80px !important;
  padding-bottom: 72px !important;
  padding-left: 10.4% !important;
}
.list_title {
  font-size: 1.0625rem;
  color: #182540;
  padding-left: 41px;
  font-family: Open Sans, sans-serif !important;
  font-size: 1.0625rem;
  color: #182540;
  margin-bottom: 0px;
  padding-bottom: 36px !important;
}
.pt-24 {
  padding-top: 24px;
}
.w-50 {
  flex-basis: 50%;
}
.h-652 img.w-100.fluid.h-100 {
  object-fit: cover;
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  -o-object-fit: cover;
  object-fit: cover;
}
.image {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  -o-object-fit: cover;
  object-fit: cover;
}
.title {
  font-family: Lora, serif !important;
  font-size: 2.625rem;
  color: #182540;
  font-weight: 500;
}
.price_tag {
  position: relative;
}
.price_tag_text {
  position: absolute;
  top: 1px;
  left: 10px;
  color: #fff;
  letter-spacing: 7px;
  font-family: Open Sans, sans-serif !important;
  font-size: 0.875rem;
}
.price {
  font-family: Lora, serif !important;
  font-size: 2.625rem;
  font-weight: 500;
  color: #182540;
}
@media screen and (min-width: 992px) and (max-width: 1366px) {
  .custom_padding {
    padding-left: 10.4% !important;
  }
}
</style>
