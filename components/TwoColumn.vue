<template>
  <div class="two-column">
    <div class="two-column__left">
      <slot name="left"></slot>
    </div>
    <div class="two-column__right">
      <slot name="right"></slot>
    </div>
  </div>
</template>

<script>
export default {
    name: "TwoColumn",
    props: {
        title: {
            type: String,
            default: "Title"
        },
        right: {
            type: String,
            default: "Text here"
        }
    }
}
</script>

<style>

</style>