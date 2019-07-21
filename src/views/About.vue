<template>
	<div class="about">
		<HeroIntro title="About me" subtitle="Learn a little about who I am" kind="is-info is-bold" />
		<section class="section">
			<Contact />
		</section>
		<section class="section">
			<Tiles />
		</section>
	</div>
</template>

<script>
	import HeroIntro from '@/components/HeroIntro';
	import Tiles from '@/components/Tiles';
	import Contact from '@/components/Contact';

	export default {
		name: 'about',
		components: {
			HeroIntro,
			Tiles,
			Contact
		}
	} 
</script>
