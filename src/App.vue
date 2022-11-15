<template>
  <Navbar v-if="!$route.meta.hideNavbar" />
  <router-view/>
  <Footer v-if="!$route.meta.hideNavbar" />
</template>

<script>
import Navbar from '@/components/Navbar.vue';
import Footer from '@/components/Footer.vue'

export default {
  components: {
    Navbar,
    Footer
  }
}
</script>

