<template>
  <div>
    <Navbar />
    <section class="main-content">
      <Nuxt />
    </section>
    <Footer />
  </div>
</template>

<script>
import Navbar from '~/components/Navbar.vue'
import Footer from '~/components/Footer.vue'
export default {
  components: {
    Navbar,
    Footer
  },
  head () {
    return {
      htmlAttrs: {
        class: 'has-navbar-fixed-top'
      }
    }
  }
}
</script>
