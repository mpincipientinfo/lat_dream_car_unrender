<template>
  <div>
    <div v-for="(service, index, count) in prop" :key="index">
      <Service :count="count" :prop="service" />
    </div>
  </div>
</template>
<script>
import Service from "./Service";
export default {
  props: ["prop"],
  components: {
    Service
  }
};
</script>
