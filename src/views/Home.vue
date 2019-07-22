<template>
  <div class="home">
    <HeroHome />
    <About />
  </div>
</template>

<script>
import HeroHome from '@/components/HeroHome';
import About from '@/components/About';

export default {
  name: 'home',
  components: {
    HeroHome,
    About
  }
}
</script>
