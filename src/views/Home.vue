<template>
	<div class="home">
		<HeroHome />
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
