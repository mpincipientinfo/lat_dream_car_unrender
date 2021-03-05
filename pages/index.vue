<template>
  <div>
    <Head class="section" id="head" :prop="pageData.section_head" />
    <Credentials class="section" id="credentials" :prop="pageData.section_referenzen" />
    <Benefits class="section" id="benefits" :prop="pageData.section_vorteile" />
    <Services class="section" id="services" :prop="pageData.section_services" />
    <Contact class="section" id="contact" :prop="pageData.section_contact" />
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
  data() {
    return {
      sectionObserver: null
    };
  },
  mounted() {
    this.observeSections();
  },
  methods: {
    observeSections() {
      const options = {
        rootMargin: "0px",
        threshold: 0
      };
      this.sectionObserver = new IntersectionObserver(this.sectionObserverHandler, options);
      // Observe each section
      const sections = document.querySelectorAll(".section");
      sections.forEach((section) => {
        this.sectionObserver.observe(section);
      });
    },
    sectionObserverHandler(sections) {
      for (const section of sections) {
        if (section.isIntersecting) {
          const sectionId = section.target.id;
          // Push sectionId to router here
          history.pushState({}, null, this.$route.path + `#${sectionId}`);
        }
      }
    }
  },
  async asyncData({ $axios }) {
    let pageData = await $axios.get("/payload/home.json").then((response) => {
      return response.data;
    });
    return { pageData: pageData };
  }
};
</script>