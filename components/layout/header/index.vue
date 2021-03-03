<template>
  <div class="d-flex justify-content-center">
    <div class="bv-example-row position-absolute header">
      <b-row class="m-0">
        <b-col sm="3">
          <b-img style="margin-top: 6px" :src="prop.image.url"> </b-img>
        </b-col>
        <b-col sm="9" align-v="center" class="d-flex justify-content-end align-self-center">
          <b-list-group horizontal>
            <nuxt-link class="links hover-text-decoration-none d-flex align-self-center" v-for="(item, index) in prop.image.page_links" :key="index" to="#">
              <b-list-group-item class="bg-transparent border-0 text-uppercase title">
                {{ item.title }}
              </b-list-group-item>
            </nuxt-link>
            <b-list-group-item class="bg-transparent border-0">
              <ButtonDanger
                :prop="{
                  text: prop.image.button,
                  path: '#'
                }"
              />
            </b-list-group-item>
          </b-list-group>
        </b-col>
      </b-row>
    </div>
  </div>
</template>
<script>
import ButtonDanger from "@/components/common/button/ButtonDanger";
export default {
  props: ["prop"],
  components: { ButtonDanger }
};
</script>
<style scoped>
.links {
  padding-left: 25px;
  padding-right: 25px;
  font-family: Open Sans, sans-serif !important;
  font-size: 1.0625rem;
  font-weight: 500 !important;
  padding-top: 0 !important;
  padding-bottom: 0 !important;
  color: #fff !important;
}
.title {
  font-size: 17px;
  font-weight: 500;
  line-height: 26px;
  padding-right: 0.5rem;
  padding-left: 0.5rem;
}
.list-group .list-group-item {
  padding: 0.75rem 0rem;
}
.header {
  width: 100%;
  padding: 0 7% 7px;
  border-bottom: 1px solid hsla(0, 0%, 100%, 0.5);
  top: 22px;
  z-index: 1;
}
.list-group-item {
  color: hsla(0, 0%, 100%, 0.5);
}
.list-group-item:hover {
  color: hsla(0, 0%, 100%, 0.75);
}
</style>
