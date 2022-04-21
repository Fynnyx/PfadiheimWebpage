<template>
  <div class="nav-dropdown" @click.prevent="isOpen = !isOpen">
    <nuxt-link to="#" class="nav-dropdown__title">{{ title }}</nuxt-link>
    <span aria-hidden="true" class="material-icons"
      >{{ isOpen ? "expand_more" : "chevron_left" }}
    </span>
    <div class="nav-dropdown__sub-menu" v-show="isOpen">
      <div
        v-for="(item, i) of items"
        :key="i"
        class="nav-dropdown__sub-menu__item"
      >
        <nuxt-link :to="item.link">{{ item.title }}</nuxt-link>
      </div>
    </div>
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
      default: false,
    },
  },
  created() {
    this.$nuxt.$on('openMobile', () => {
      this.isOpen = !this.isOpen
    })
  }
};
</script>

<style lang="scss" scoped>
nav .nav-dropdown .nav-dropdown__sub-menu {
  z-index: 10;
  position: absolute;
  background-color: $red-5;
  border-bottom-left-radius: 0.5rem;
  border-bottom-right-radius: 0.5rem;
  top: calc(100%);
  left: 50%;
  transform: translateX(-50%);
  width: max-content;
  box-shadow: 0 8px 8px rgb(10 10 10 / 10%);
}
.nav-dropdown__sub-menu__item {
  padding: 10px 20px;
  display: flex;

  &:hover {
    border-bottom: solid 0.1rem;
    border-bottom-color: $black;
    &:last-child {
      border-bottom-left-radius: 0.5rem;
      border-bottom-right-radius: 0.5rem;
    }
    a {
      text-decoration: underline;
    }
  }
}
.nav-dropdown {
  &__title {
    align-self: center;
  }
  &:hover {
    cursor: pointer;
    a.nav-dropdown__title {
      text-decoration: underline;
    }
  }
  display: flex;
}

@media screen and (max-width: $sm) {
  .nav-dropdown {
    &__sub-menu {
      margin-left: 2rem;

    }
    width: 100%
  }
}
</style>
