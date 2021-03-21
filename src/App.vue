<template>
  <v-app>
    <Navbar></Navbar>
    <v-main> 
      <router-view />
    </v-main>
    <v-btn
      v-scroll="onScroll"
      v-show="back"
      fab
      dark
      fixed
      bottom
      right
      color="primary"
      title="Back to the top"
      @click="toTop"
      >
      <v-icon>mdi-arrow-up-bold</v-icon>
    </v-btn>
    <Footer></Footer>
  </v-app>
</template>

<script>
import Navbar from "./components/Navbar";
import Footer from "./components/Footer";

export default {
  name: "App",
  components: {
    Navbar,
    Footer
  },
  data() {
    return {
      back: false
    }
  },
  methods: {
    onScroll (e) {
      if (typeof window === 'undefined') return
      const top = window.pageYOffset ||   e.target.scrollTop || 0
      this.back = top > 20
    },
    toTop () {
      this.$vuetify.goTo(0)
    }
  }
};
</script>
<style>
@import './css/style.css';
</style>
