<template>
  <div class="about">
    <HeroIntro title="About me" subtitle="Learn a little about who I am" />
    <Tiles />
  </div>
</template>

<script>
import HeroIntro from '@/components/HeroIntro';
import Tiles from '@/components/Tiles';

export default {
  name: 'about',
  components: {
    HeroIntro,
    Tiles
  }
}
</script>
