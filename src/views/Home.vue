<template>
	<div class="home">
		<HeroHome />
		<div class="spacer"></div>
		<About />
		<Footer />
	</div>
</template>

<script>
import HeroHome from "@/components/home/HeroHome";
import About from "@/components/home/About";
import Footer from "@/components/layout/Footer";

export default {
	name: "home",
	components: {
		HeroHome,
		About,
		Footer
	}
};
</script>

<style scoped>

.spacer {
	aspect-ratio: 700/100;
	width: 100%;
	background-repeat: no-repeat;
	background-position: center;
	background-size: cover;
	background-image: url('../assets/img/waves.svg');
}

@media (max-width: 768px) {
	.spacer {
		aspect-ratio: 500/200;
	}
}
</style>
