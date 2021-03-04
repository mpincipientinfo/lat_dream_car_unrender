<template>
  <div>
    <div align-v="center" class="d-flex justify-content-center align-self-center">
      <div class="list-group list-group-horizontal">
        <nuxt-link to="/#" class="btn d-flex align-self-center link p-0" v-for="(link, index) in prop" :key="index">
          <div class="list-group-item list-item bg-transparent border-0 p-0">
            {{ link.title }}
          </div>
        </nuxt-link>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: ["prop"]
};
</script>
<style scoped>
.link {
  font-family: Open Sans, sans-serif !important;
  font-weight: 600;
  color: #182540;
}
.list-item {
  padding: 0px 25px !important;
  font-size: 17px;
}
</style>