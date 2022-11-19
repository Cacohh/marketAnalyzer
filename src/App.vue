<template>
  <Header v-if="!$route.meta.hideHeader" />
  <Navbar v-if="!$route.meta.hideNavbar" />
  <router-view/>
  <Footer v-if="!$route.meta.hideFooter" />
</template>

<script>
import Navbar from '@/components/Navbar.vue';
import Footer from '@/components/Footer.vue';
import Header from '@/components/Header.vue'

export default {
  components: {
    Navbar,
    Footer,
    Header
  }
}
</script>

