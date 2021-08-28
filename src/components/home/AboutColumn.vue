<template>
	<div class="column">
		<div class="about-column">
			<font-awesome-icon class="fa-3x column-icon" :icon="[content.iconType, content.icon]" />
			<br />
			<p class="column-title">{{ content.title }}</p>
			<p class="column-subtitle">{{ content.subtitle }}</p>
			<div class="feature-set" v-for="set in content.featureSets" :key="set.title">
				<p class="column-feature-title">{{ set.title }}</p>
				<p class="column-feature" v-for="feature in set.features" :key="feature">{{ feature }}</p>
			</div>
		</div>
	</div>
</template>

<script>
import { library } from "@fortawesome/fontawesome-svg-core";
import { faUser } from "@fortawesome/free-regular-svg-icons";
import { faLaptopCode } from "@fortawesome/free-solid-svg-icons";
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";

library.add(faUser, faLaptopCode);

export default {
	name: "About Column",
	props: ["content"],
	components: {
		FontAwesomeIcon,
	},
};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Roboto+Mono:wght@700&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Source+Sans+Pro&display=swap");
.about-column {
	width: 100%;
	padding: 50px;
	background-color: #fff;
	border-bottom: 1px solid #e6ecf8;
	border-right: 1px solid #e6ecf8;
	text-align: center;
	/* box-shadow: 0 5px 5px 0 rgba(233, 240, 243, 0.5), 0 0 0 1px #e6ecf8; */
	height: 100%;
}

.column {
	padding: 0;
}

.column-icon {
	margin-bottom: 30px;
	color: #3273dc;
}
.column-title {
	font-size: 18px;
	color: #222;
	font-family: "Roboto Mono", monospace;
	text-transform: uppercase;
}
.column-subtitle {
	margin-top: 30px;
}
.column-feature-title {
	font-size: 16px;
	color: #555;
	font-family: "Roboto Mono", monospace;
	text-transform: uppercase;
	margin-top: 30px;
	margin-bottom: 30px;
}
.column-feature {
	font-size: 16px;
	color: #444;
	margin: 4px 0;
	font-family: "Source Sans Pro", sans-serif;
}
</style>