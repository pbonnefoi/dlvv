<template>
  <nav class="navbar is-spaced has-shadow is-fixed-top" role="navigation" aria-label="main navigation">
    <div class="navbar-brand">
      <nuxt-link to="/" class="navbar-item">
        DLVV
      </nuxt-link>

      <a
        role="button"
        class="navbar-burger"
        aria-label="menu"
        aria-expanded="false"
        data-target="navbarBasicExample"
        @click="$store.dispatch('nav/toggleSidebar')"
      >
        <span aria-hidden="true" />
        <span aria-hidden="true" />
        <span aria-hidden="true" />
      </a>
    </div>

    <div id="navbarBasicExample" class="navbar-menu">
      <div class="navbar-end">
        <div class="navbar-item">
          <div class="buttons">
            <nuxt-link to="/signin" class="button">
              <strong>S'inscrire</strong>
            </nuxt-link>
            <nuxt-link to="/logout" class="button is-light">
              <strong>Se déconnecter</strong>
            </nuxt-link>
          </div>
        </div>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  computed: {
    isSidebar () {
      return this.$store.getters['nav/toggleSidebar']
    }
  },
  watch: {
    '$route' () {
      if (process.client && this.isSidebar && window.innerWidth < 768) {
        this.$store.dispatch('nav/toggleSidebar')
      }
    }
  }
}
</script>
