<template>
  <div>
    <navbar />
    <nuxt />
    <Footer />
  </div>
</template>

<script>
import Navbar from '../components/Navbar'
import Footer from '../components/Footer.vue'
export default {
  components: {
    Navbar,
    Footer
  }
}
</script>
<style>
</style>
