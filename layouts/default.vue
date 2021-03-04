<template>
  <div>
    <Header :prop="pageData.section_navbar" />
    <Nuxt />
    <Footer :prop="pageData.section_footer" />
  </div>
</template>
<script>
import Header from "@/components/layout/header";
import Footer from "@/components/layout/footer";
export default {
  components: {
    Header,
    Footer
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