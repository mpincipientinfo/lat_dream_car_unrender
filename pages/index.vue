<template>
  <div>
    <Head :prop="pageData.section_head" />
  </div>
</template>
<script>
import Head from "@/components/home/head";
export default {
  components: { Head },
  async asyncData({ $axios }) {
    let pageData = await $axios.get("/payload/home.json").then((response) => {
      return response.data;
    });
    return { pageData: pageData };
  }
};
</script>