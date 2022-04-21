<template>
  <nav class="navbar__list">
    <div class="navbar__list__logo">
      <nuxt-link to="/">
        <img src="~/assets/images/logo.png" alt="logo" />
      </nuxt-link>
    </div>
    <div class="navbar__list__burger">
      <button @click="[(mobileOpen = !mobileOpen), $nuxt.$emit('openMobile')]">
        <span class="material-icons" aria-hidden="true">menu</span>
      </button>
    </div>
    <div class="navbar__list__dropdowns">
      <div
        class="navbar__list__item"
        :class="{ 'navbar__list__item--open': mobileOpen }"
      >
        <nuxt-link to="/" class="navbar__list__item__title">Home</nuxt-link>
      </div>
      <div
        class="navbar__list__item"
        :class="{ 'navbar__list__item--open': mobileOpen }"
      >
        <NavDropdown
          title="Pfadiheim"
          :items="[
            {
              title: 'Home',
              link: '/',
            },
            {
              title: 'Anreise',
              link: '/anreise',
            },
            {
              title: 'Umgebung',
              link: '/umgebung',
            },
          ]"
        />
      </div>
      <div
        class="navbar__list__item"
        :class="{ 'navbar__list__item--open': mobileOpen }"
      >
        <NavDropdown
          title="Miete + Preise"
          :items="[
            {
              title: 'Preise',
              link: '/preise',
            },
          ]"
        />
      </div>
      <div
        class="navbar__list__item"
        :class="{ 'navbar__list__item--open': mobileOpen }"
      >
        <NavDropdown
          title="Administratives"
          :items="[
            {
              title: 'Vertrag',
              link: '/vertrag',
            },
            {
              title: 'Schlussreinigung',
              link: '/schlussreinigung',
            },
            {
              title: 'Heimordung',
              link: '/heimordung',
            },
          ]"
        />
      </div>
      <div
        class="navbar__list__item"
        :class="{ 'navbar__list__item--open': mobileOpen }"
      >
        <NavDropdown
          title="Verein"
          :items="[
            {
              title: 'Mitglieder',
              link: '/mitglieder',
            },
            {
              title: 'Statuten',
              link: '/statuten',
            },
            {
              title: 'Geschichte',
              link: '/geschichte',
            },
          ]"
        />
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: "NavBar",
  props: {
    mobileOpen: {
      type: Boolean,
      default: false,
    },
  },
  created() {},
};
</script>
<style lang="scss" scoped>
.navbar {
  &__list {
    &__logo {
      img {
        width: 2rem;
      }
    }
    &__burger {
      display: none;
    }
    &__dropdowns {
      display: flex;
      flex-direction: row;
    }
    &__item {
      color: $black;
      padding: 10px 20px;
      position: relative;
      text-align: center;
      display: flex;
      transition: 0.4;
      a:hover {
        text-decoration: underline;
      }
      a {
        color: inherit;
        text-decoration: none;
      }
    }
    display: flex;
    align-items: center;
    justify-content: left;
    padding-left: 1rem;
  }
  display: flex;
}

@media screen and (max-width: $sm) {
  .nav-dropdown {
    &__title {
      border-bottom: solid $black-40;
    }
    &__sub-menu {
      display: block;
    }
  }
  .navbar {
    &__list {
      &__burger {
        button {
          background-color: transparent;
          border: none;
          width: 100%;
          &:hover {
            cursor: pointer;
          }
        }
        display: block;
      }
      &__dropdowns {
        display: flex;
        flex-direction: row;
        // align-self: ;
      }
      &__item {
        &--open {
          display: flex;
          flex-direction: column;
        }
        display: none;
      }
      display: flex;
      flex-direction: row;
    }
    display: flex;
  }
}
</style>