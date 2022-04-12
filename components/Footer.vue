<template>
  <div class="footer">
    <span> Copyright by Pfadiheimverein Baden</span>
  </div>
</template>

<script>
export default {
  name: "Footer",
};
</script>

<style lang="scss" scoped>
.footer {
  display: flex;
  justify-content: center;
  align-items: center;
  position: absolute;
  bottom: 0;
  width: 100%;
  height: 60px;
  background: $black-90;
  > span {
      font-size: 12px;
  }
}
</style>