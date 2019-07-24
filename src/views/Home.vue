<template>
  <div class="home">
    <HeroHome />
    <About />
    <Footer />
  </div>
</template>

<script>
import HeroHome from '@/components/HeroHome';
import About from '@/components/About';
import Footer from '@/components/Footer';

export default {
  name: 'home',
  components: {
    HeroHome,
    About,
    Footer
  }
}
</script>
