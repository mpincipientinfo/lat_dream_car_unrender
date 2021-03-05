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
import index from "@/components/pages/index";
export default {
  components: {
    Head: index.Head,
    Credentials: index.Credentials,
    Benefits: index.Benefits,
    Services: index.Services,
    Contact: index.Contact
  },
  async asyncData({ $axios }) {
    let pageData = await $axios.get("/payload/home.json").then((response) => {
      return response.data;
    });
    return { pageData: pageData };
  }
};
</script>