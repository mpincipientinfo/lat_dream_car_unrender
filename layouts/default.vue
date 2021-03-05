<template>
  <div>
    <Header class="section" id="header" :prop="pageData.section_navbar" />
    <Nuxt />
    <Footer class="section" id="footer" :prop="pageData.section_footer" />
  </div>
</template>
<script>
import layout from "@/components/layout";
export default {
  components: {
    Header: layout.Header,
    Footer: layout.Footer
  },
  data() {
    return {
      pageData: {}
    };
  },
  async fetch() {
    this.pageData = await this.$axios.get("/payload/shared.json").then((response) => {
      return response.data;
    });
  }
};
</script>