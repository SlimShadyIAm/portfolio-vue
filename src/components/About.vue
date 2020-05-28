<template>
	<div id="about">
		<HeroIntro
			title="About me"
			subtitle="Learn a little about who I am"
			kind="is-info"
		/>
		<section class="section">
			<AboutColumns />
		</section>
	</div>
</template>

<script>
import HeroIntro from "@/components/HeroIntro";
import AboutColumns from "@/components/AboutColumns";
// import Tiles from "@/components/Tiles";

export default {
	name: "about",
	components: {
		HeroIntro,
		AboutColumns
		// Tiles
	}
};
</script>
