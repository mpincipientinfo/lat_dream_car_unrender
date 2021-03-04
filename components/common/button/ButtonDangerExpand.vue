<template>
  <nuxt-link :to="prop.path">
    <b-button class="btn-danger-expand" :class="prop.addBtnClass"> {{ prop.text }} </b-button>
  </nuxt-link>
</template>
<script>
export default {
  props: ["prop"]
};
</script>
<style scoped>
.btn-danger-expand:hover {
  background: linear-gradient(90deg, #730309, #e50612) !important;
  transition: all 0.5s !important;
  width: 262px;
  letter-spacing: 2px;
}
.btn-danger-expand {
  transition: all 0.5s !important;
  width: 223px;
  border-radius: 60px !important;
  background: linear-gradient(90deg, #e50612, #730309) !important;
  color: #fff !important;
  text-align: center !important;
  padding: 12px;
  border: 0;
  overflow: hidden;
  position: relative;
  z-index: 1;
  font-family: Open Sans, sans-serif !important;
  font-size: 18px;
  line-height: 27px;
  height: 59px;
}
@media screen and (min-width: 992px) and (max-width: 1366px) {
  .btn-danger-expand:hover {
    width: 240px;
  }
}
</style>