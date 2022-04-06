<template>
  <ul class="navbar__list">
    <li class="navbar__list__logo">
      <nuxt-link to="/">
        <img src="~/assets/images/logo.png" alt="logo" />
      </nuxt-link>
    </li>
    <li>
      <div class="navbar__list__item">
        <nuxt-link to="/" class="navbar__list__item__title">Home</nuxt-link>
      </div>
    </li>
    <li>
      <NavDropdown
        title="Pfadiheim"
        :items="[
          {
            title: 'Home',
            link: '/',
          },
          {
            title: 'Anreise',
            link: '/pfadiheim/anreise',
          },
          {
            title: 'Umgebung',
            link: '/pfadiheim/umgebung',
          },
          {
            title: 'Rundgang',
            link: '/pfadiheim/rundgang',
          },
        ]"
      />
    </li>
    <li>
      <NavDropdown
        title="Miete + Preise"
        :items="[
          {
            title: 'Preise',
            link: '/preise',
          },
        ]"
      />
    </li>
    <li>
      <NavDropdown
        title="Administratives"
        :items="[
          {
            title: 'Vertrag',
            link: 'admin/vertrag',
          },
          {
            title: 'Schlussreinigung',
            link: 'admin/schlussreinigung',
          },
          {
            title: 'Heimordung',
            link: 'admin/heimordung',
          }
        ]"
      />
    </li>
    <li>
      <NavDropdown 
        title="Verein"
        :items="[
          {
            title: 'Mitglieder',
            link: '/verein/mitglieder',
          },
          {
            title: 'Statuten',
            link: '/verein/statuten',
          },
          {
            title: 'Geschichte',
            link: '/verein/geschichte',
          }
        ]"   
      />
    </li>
    <li>
      <div class="navbar__reservation">
        <nuxt-link to="/reservation"
          ><button>
            <span>Zur Anfrage</span>
            <span class="material-icons"> chevron_right </span>
          </button></nuxt-link
        >
      </div>
    </li>
  </ul>
</template>

<script>
export default {
  name: "NavBar",
};
</script>

<style lang="scss" scoped>
.navbar {
  &__list {
    &__logo {
      img {
        height: 2rem;
        width: auto;
      }
      align-items: center;
    }
    &__item {
      &__title {
        &:hover {
          text-decoration: underline;
        }
        padding-bottom: 0.75rem;
        text-decoration: none;
      }
    }
    display: flex;
    flex-direction: row;
    gap: 1rem;
    align-items: center;
    list-style: none;
    border-bottom: solid $black-20 0.125rem;
  }
  &__reservation {
    a {
      text-decoration: none;
    }
    button {
      .material-icons {
        align-self: center;
      }
      &:hover {
        cursor: pointer;
      }
      display: flex;
      justify-content: center;
      align-items: center;
      background-color: $red-80;
      border-radius: 0.25rem;
      border: $black-20 solid 0.125rem;
    }
    margin-left: auto;
  }
}
</style>