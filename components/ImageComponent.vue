<template>
  <div class="image-component">
      <img :src="getImage()" :alt="alt" />
      <p class="footnote">
          {{footnote}}
      </p>
  </div>
</template>

<script>
export default {
  name: "ImageComponent",
  props: {
    src: {
      type: String,
      required: true,
    },
    alt: {
      type: String,
      required: true,
    },
    footnote: {
        type: String,
        required: false,
    },
  },
  methods: {
    getImage() {
      return require("~/assets/images/" + this.src);
    },
  },
};
</script>

<style>
</style>