<template>
	<div id="about">
		<HeroIntro
			kind="is-info" style="padding-bottom: 200px;"
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