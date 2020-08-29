<template>
	<section class="section" style="padding: 0;">
		<div class="container">
			<div class="columns columns-contributions">
				<Contribution
					v-for="contribution in contributions"
					:key="contribution.id"
					:contribution="contribution"
				/>
			</div>
		</div>
	</section>
</template>

<script>
import Contribution from "@/components/previouswork/Contribution.vue";
import uuid from "uuid";

export default {
	name: "Contributions",
	components: {
		Contribution
	},
	data() {
		return {
			contributions: [
				{
					id: uuid.v4(),
					name: "GetSileo.app",
					description:
						"Website for the iOS Jailbreak package manager, Sileo, made by Coolstar.",
					url: "https://getsileo.app",
					image: require("@/assets/img/contributions/sileo.jpg")
				},
				{
					id: uuid.v4(),
					name: "Parcility",
					description:
						"The single place to find the most popular Jailbreak tweak repositories and packages.",
					url: "https://parcility.co",
					image: require("@/assets/img/contributions/parcility.png")
				}
			]
		};
	}
};
</script>

<style>
@media screen and (max-width: 1024px), print {
	.columns-contributions {
		flex-direction: column;
	}
}
</style>
