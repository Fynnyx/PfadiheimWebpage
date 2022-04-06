<template>
  <div class="nav-dropdown">
    <ul>
      <li @click.prevent="toggle" class="nav-dropdown__title">
        <span>{{ title }}</span>
        <span class="material-icons">{{
          isOpen ? "expand_more" : "chevron_left"
        }}</span>
      </li>
      <li
        class="nav-dropdown__items"
        v-show="isOpen"
        v-for="item in items"
        :key="item.link"
      >
        <nuxt-link to="/">{{ item.title }}</nuxt-link>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "NavDropdown",
  props: {
    title: {
      type: String,
      required: true,
    },
    items: {
      type: Array,
      required: true,
    },
    isOpen: {
      type: Boolean,
      required: true,
    },
  },
  methods: {
    toggle() {
      this.isOpen = !this.isOpen;
    },
  },
};
</script>

<style lang="scss" scoped>
.nav-dropdown {
  > ul {
    list-style: none;
    align-items: center;
    justify-content: center;
    padding: 0;
  }
  &__title {
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  &__items {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: flex-start;
    padding: 0.5rem;
    a {
      text-decoration: none;
    }
    &:hover {
      background-color: $black-10;
      a {
        text-decoration: underline;
      }
    }
  }
}
</style>