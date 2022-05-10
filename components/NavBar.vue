<template>
  <nav class="navbar">
    <template>
      <b-navbar>
        <template #brand>
          <b-navbar-item tag="router-link" :to="{ path: '/' }">
            <img src="~/assets/images/logo.png" alt="Pfadiheim Baden Logo" />
          </b-navbar-item>
        </template>
        <template #start >
          <div
            class="navbar-for"
            v-for="navbaritem in navbar"
            :key="navbaritem.title"
          >
            <b-navbar-dropdown
              v-if="navbaritem.children.length !== 0"
              :label="navbaritem.title"
              class="is-hoverable"
            >
              <nuxt-link
                v-for="page in navbaritem.children"
                :key="page.title"
                :to="page.href"
                class="navbar-item"
              >
                {{ page.title }}
              </nuxt-link>
            </b-navbar-dropdown>
            <nuxt-link v-else :to="navbaritem.href" class="navbar-item">
              {{ navbaritem.title }}
            </nuxt-link>
          </div>
        </template>

        <template #end></template>
      </b-navbar>
    </template>
  </nav>
</template>

<script>
import { navbar } from "~/assets/static/navbar.js";
export default {
  props: {
    navbar: {
      type: Array,
      default: () => navbar,
    },
  },
};
</script>

<style>
</style>