<template>
  <div>
    <Header :prop="pageData.section_navbar" />
    <Nuxt />
  </div>
</template>
<script>
import params from "@/config/params.js";
import Header from "@/components/layout/header";
export default {
  components: {
    Header
  },
  data() {
    return {
      pageData: {}
    };
  },
  async fetch() {
    this.pageData = await this.$axios
      .get(params.baseUrl + "/payload/shared.json")
      .then((response) => {
        return response.data;
      });
  }
};
</script>