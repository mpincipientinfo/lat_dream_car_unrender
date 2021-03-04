<template>
  <div class="benefit_parent d-flex flex-column align-items-center justify-content-center">
    <h3 class="subtitle mb-1">{{ prop.subtitle }}</h3>
    <h2 class="title pt-4 pb-6">{{ prop.title }}</h2>
    <b-container class="bv-example-row">
      <b-row>
        <b-col lg="3" sm="6" v-for="(benefit, index) in prop.vorteile" :key="index">
          <Benefit :prop="benefit" :index="index + 1" />
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>
<script>
import Benefit from "./Benefit";
export default {
  props: ["prop"],
  components: {
    Benefit
  }
};
</script>
<style scoped>
.benefit_parent {
  background-color: #182540;
  color: #fff;
  padding-bottom: 80px;
}
.subtitle {
  font-size: 1.125rem;
  font-weight: 600;
  padding-top: 140px;
  font-family: "Mulish", sans-serif;
  margin-bottom: 8px !important;
}
.title {
  font-family: Lora, serif !important;
  font-size: 2.625rem;
  padding-bottom: 60px;
  padding-top: 20px !important;
}
</style>
