<template>
  <div class="default-content">
    <h1>Wilkommen im Pfadiheim Baden</h1>
    <nuxt-content :document="doc" />
  </div>
</template>

<script>
export default {
  name: "IndexPage",
  layout: "default",
  async asyncData({ $content, params }) {
    const doc = await $content("index").fetch();
    return ({doc})
  }
};
</script>
