<template>
  <div class="footer">
    <div class="d-flex flex-column">
      <div class="text-center">
        <div class="text-center">
          <div class="mb-3">
            <img alt="image" class="img-fluid" :src="prop.image.url" />
          </div>
          <div>
            <img src="@/assets/images/logoline.f940fa9.png" alt="Image" />
          </div>
          <p class="title mt-3 pt-1 mb-3">{{ prop.title }}</p>
          <!-- page links -->
          <LinkList :prop="prop.page_links" class="text-uppercase pt-40" />
          <!--legal links -->
          <LinkList :prop="prop.legal_links" />
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import LinkList from "./LinkList";
export default {
  props: ["prop"],
  components: {
    LinkList
  }
};
</script>
<style scoped>
.title {
  color: #182540;
  font-family: Open Sans, sans-serif !important;
  font-size: 1.0625rem;
}
.pt-40 {
  padding-top: 40px;
  padding-bottom: 12px;
}
</style>
