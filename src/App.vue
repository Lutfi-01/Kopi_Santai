<template>
  <div>
    <Navbar />
    <SplashScreen v-if="loading" />
    <div v-else>
      <Home />
      <About />
      <Menu />
      <Gallery />
      <Testimonials />
      <Contact />
      <Footer />
    </div>
  </div>
</template>

<script>
import { ref, onMounted } from 'vue'
import Navbar from './components/Navbar.vue'
import SplashScreen from './components/SplashScreen.vue'
import Footer from './components/Footer.vue'
import Home from './pages/Home.vue'
import About from './pages/About.vue'
import Menu from './pages/Menu.vue'
import Gallery from './pages/Gallery.vue'
import Testimonials from './pages/Testimonials.vue'
import Contact from './pages/Contact.vue'

export default {
  components: { SplashScreen, Navbar, Footer, Home, About, Menu, Gallery, Contact, Testimonials },
  data() {
    return {
      loading: true
    }
  },
  mounted() {
    setTimeout(() => {
      this.loading = false;
    }, 3000);
  }
}
</script>