<template>
  <div class="footer">
    <span> {{ footer }}</span>
  </div>
</template>

<script>
const { footer } =  require("assets/static/properties.js");
export default {
  name: "Footer",
  props: {
    footer: {
      type: String,
      default: footer
    }
  }
};
</script>

<style lang="scss" scoped>
.footer {
  // position: fixed;
  bottom: 0;
  
  display: flex;
  justify-content: center;
  align-items: center;
  // position: absolute;
  bottom: 0;
  width: 100%;
  height: 60px;
  background: $black-90;
  > span {
      font-size: 12px;
  }
}
</style>