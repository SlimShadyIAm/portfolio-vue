<template>
	<div class="work">
		<HeroIntro
			title="My Previous Work"
			subtitle="A showcase of my past designs, projects"
			kind="is-info"
		/>
		<div class="container">
			<section class="section">
				<h2 class="title">Contributions</h2>
				<Contributions />
				<br>
				<h2 class="title">Projects</h2>
				<WorkObjects />
			</section>
		</div>
		<Footer />
	</div>
</template>

<script>
import HeroIntro from "@/components/layout/HeroIntro";
import WorkObjects from "@/components/previouswork/WorkObjects";
import Contributions from "@/components/previouswork/Contributions";
import Footer from "@/components/layout/Footer";

export default {
	name: "PastWork",
	components: {
		HeroIntro,
		WorkObjects,
		Contributions,
		Footer
	}
};
</script>
