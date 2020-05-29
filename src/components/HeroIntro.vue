<template>
	<section class="hero" :class="kind">
		<div class="hero-body">
			
		</div>
	</section>
</template>

<script>
export default {
	name: "heroIntro",
	props: ["title", "subtitle", "kind"]
};
</script>

<style scoped>
	.hero {
		padding-bottom: 200px;
	}
</style>

