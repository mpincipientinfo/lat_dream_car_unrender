<template>
  <div>
    <a :href="prop.href" class="social_meta" :target="prop.target">
      <img :src="require(`@/assets/images/${prop.image}`)" />
      <p class="mt-3">{{ prop.text }}</p>
    </a>
  </div>
</template>
<script>
export default {
  props: ["prop"]
};
</script>
<style scoped>
.social_meta:hover,
.social_meta {
  color: #030508;
  text-decoration: none;
}
</style>
