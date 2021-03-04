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
import home from "@/components/home";
export default {
  components: {
    Head: home.Head,
    Credentials: home.Credentials,
    Benefits: home.Benefits,
    Services: home.Services,
    Contact: home.Contact
  },
  async asyncData({ $axios }) {
    let pageData = await $axios.get("/payload/home.json").then((response) => {
      return response.data;
    });
    return { pageData: pageData };
  }
};
</script>