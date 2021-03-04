<template>
  <div>
    <Head :prop="pageData.section_head" />
    <Credentials :prop="pageData.section_referenzen" />
    <Benefits :prop="pageData.section_vorteile" />
  </div>
</template>
<script>
import Head from "@/components/home/head";
import Credentials from "@/components/home/credentials";
import Benefits from "@/components/home/benefits";
export default {
  components: { Head, Credentials, Benefits },
  async asyncData({ $axios }) {
    let pageData = await $axios.get("/payload/home.json").then((response) => {
      return response.data;
    });
    return { pageData: pageData };
  }
};
</script>