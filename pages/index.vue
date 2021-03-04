<template>
  <div>
    <Head :prop="pageData.section_head" />
    <Credentials :prop="pageData.section_referenzen" />
    <Benefits :prop="pageData.section_vorteile" />
    <Services :prop="pageData.section_services" />
    <Contact :prop="pageData.section_contact" />
  </div>
</template>
<script>
import Head from "@/components/home/head";
import Credentials from "@/components/home/credentials";
import Benefits from "@/components/home/benefits";
import Services from "@/components/home/services";
import Contact from "@/components/home/contact";
export default {
  components: { Head, Credentials, Benefits, Services, Contact },
  async asyncData({ $axios }) {
    let pageData = await $axios.get("/payload/home.json").then((response) => {
      return response.data;
    });
    return { pageData: pageData };
  }
};
</script>