<template>
	<div id="about">
		<section class="section xd">
			<AboutColumns />
		</section>
	</div>
</template>

<script>
import AboutColumns from "@/components/home/AboutColumns";

export default {
	name: "about",
	components: {
		AboutColumns,
	},
};
</script>

<style scoped>
.xd {
	background-color: #209cee;
}
</style>