<template>
  <div class="default-content">
      <nuxt-content :document="doc" />
  </div>
</template>

<script>
const { titleExtention } = require('./../assets/static/properties')
export default {
    async asyncData( {$content, params }) {
        const doc = await $content(params.slug || "error").fetch()
        return { doc }
    },
    head() {
        return {
            title: `${this.doc.title}${titleExtention}`,
        };
    },
}
</script>

<style>

</style>