<template>
	<div id="about">
		<HeroIntro
			kind="is-info" style="padding-bottom: 190px;"
		/>
		<section class="section">
			<AboutColumns />
		</section>
	</div>
</template>

<script>
import HeroIntro from "@/components/layout/HeroIntro";
import AboutColumns from "@/components/home/AboutColumns";

export default {
	name: "about",
	components: {
		HeroIntro,
		AboutColumns
	}
};
</script>