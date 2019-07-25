<template>
	<div id="about">
		<HeroIntro
			title="About me"
			subtitle="Learn a little about who I am"
			kind="is-info"
		/>
		<section class="section">
			<Tiles />
		</section>
	</div>
</template>

<script>
import HeroIntro from "@/components/HeroIntro";
import Tiles from "@/components/Tiles";

export default {
	name: "about",
	components: {
		HeroIntro,
		Tiles
	}
};
</script>
