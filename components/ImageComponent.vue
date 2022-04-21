<template>
    <!-- <div> -->
    <!-- </div> -->
  <img :src="`_nuxt/assets/images/${src}`" :alt="alt">
</template>

<script>
export default {
    name: "ImageComponent",
    props: {
        src: {
            type: String,
            default: ""
        },
        alt: {
            type: String,
            default: ""
        }
    },
}
</script>

<style>

</style>