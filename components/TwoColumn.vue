<template>
  <div class="two-column" :class="[{ 'two-column--head': isHead }, { 'small' : small}]">
    <div class="two-column__title">
      <span>{{ title }}</span>
    </div>
    <div class="two-column__value">
      <span v-html="getValue"></span>
      <div v-for="(s, i) in sections" :key="i" class="two-column__section">
        <span v-html="convertToMarkdown(s)"></span>
      </div>
    </div>
  </div>
</template>

<script>
import { marked } from "marked";

export default {
  name: "TwoColumn",
  components: {},
  props: {
    title: {
      type: String,
    },
    value: {
      type: String,
    },
    sections: {
      type: Array,
    },
    isHead: {
      type: Boolean,
      default: false,
    },
    small: {
      type: Boolean,
      default: false,
    }
  },
  computed: {
    getValue() {
      return marked.parseInline(this.value, { breaks: true });
    },
  },
  methods: {
    convertToMarkdown(text) {
      return marked.parseInline(text, { breaks: true });
    },
  },
};
</script>
<style lang="scss" scoped>
</style>
