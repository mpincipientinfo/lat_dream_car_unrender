<template>
  <nuxt-link :to="buttonData.path">
    <b-button class="btn-danger">{{ buttonData.text }}</b-button>
  </nuxt-link>
</template>
<script>
export default {
  props: ["prop"],
  data() {
    return {
      buttonData: this.prop
    };
  }
};
</script>
<style scoped>
.btn-danger {
  border-radius: 60px !important;
  background: linear-gradient(90deg, #e50612, #730309) !important;
  color: #fff !important;
  text-align: center !important;
  padding: 18px 60px;
  border: 0;
  overflow: hidden;
  position: relative;
  z-index: 1;
  font-family: Open Sans, sans-serif !important;
  font-size: 1.125rem;
}
.btn-danger:before {
  position: absolute;
  content: "";
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  background: linear-gradient(90deg, #730309, #e50612) !important;
  z-index: -1;
  transition: opacity 0.5s linear;
  opacity: 0;
}
.btn-danger:hover:before {
  opacity: 1;
}
</style>