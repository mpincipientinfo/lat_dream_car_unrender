<template>
  <div>
    <Main :prop="prop" />
    <Socials />
    <!-- copyright -->
    <div class="copyright text-center">
      <h6 class="copyright_text">©copyright {{ new Date().getFullYear() }} M2-wunschauto . All Rights Reserved</h6>
    </div>
  </div>
</template>
<script>
import Main from "./Main";
import Socials from "./socials";
export default {
  props: ["prop"],
  components: {
    Socials,
    Main
  }
};
</script>
<style scoped>
.copyright_text {
  font-family: Open Sans, sans-serif !important;
  font-size: 0.875rem;
  margin-bottom: 0px;
  color: #fff;
}
.copyright {
  background-color: #182540;
  padding-top: 11px;
  padding-bottom: 10px;
}
.footer {
  padding: 100px 0px;
}
</style>
