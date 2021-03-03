<template>
  <div>
    <Head :prop="pageData.section_head" />
    <Credentials :prop="pageData.section_referenzen" />
  </div>
</template>
<script>
import Head from "@/components/home/head";
import Credentials from "@/components/home/credentials";
export default {
  components: { Head, Credentials },
  async asyncData({ $axios }) {
    let pageData = await $axios.get("/payload/home.json").then((response) => {
      return response.data;
    });
    return { pageData: pageData };
  }
};
</script>