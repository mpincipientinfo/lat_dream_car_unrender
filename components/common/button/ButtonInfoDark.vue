<template>
  <nuxt-link :to="prop.path">
    <b-button class="btn-info-dark" :class="prop.addBtnClass"> {{ prop.text }} </b-button>
  </nuxt-link>
</template>
<script>
export default {
  props: ["prop"]
};
</script>
<style scoped>
.btn-info-dark {
  border-radius: 60px;
  background: transparent;
  color: #fff;
  text-align: center;
  padding: 18px 60px;
  background-color: #182540 !important;
  color: #fff !important;
  text-decoration: none !important;
  border: 0;
  transition: all 0.2s ease-out;
  font-size: 1.125rem;
}
.btn-info-dark:hover {
  background-color: #1c2b4b !important;
  transition: all 0.2s ease-out;
}
</style>