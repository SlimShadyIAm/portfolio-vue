<template>
	<div>
		<div class="columns">
			<div class="column contact-icon">
				<a href="https://github.com/SlimShadyIAm">
					<div class="box">
						<span class="icon is-large has-text-white">
							<font-awesome-icon class="fa-2x" :icon="['fab', 'github']" />
						</span>
					</div>
				</a>
			</div>
			<div class="column contact-icon">
				<a href="https://www.linkedin.com/in/farooqaamir">
					<div class="box">
						<span class="icon is-large has-text-white">
							<font-awesome-icon class="fa-2x" :icon="['fab', 'linkedin']" />
						</span>
					</div>
				</a>
			</div>
			<div class="column contact-icon">
				<a href="mailto:me@aamirfarooq.dev?">
					<div class="box">
						<span class="icon is-large has-text-white">
							<font-awesome-icon class="fa-2x" :icon="['fas', 'envelope']" />
						</span>
					</div>
				</a>
			</div>
		</div>
		<div class="columns">
			<div class="column">
				<router-link to="/work" class="box box-work">View my past work</router-link>
			</div>
		</div>
	</div>
</template>

<script>
import { library } from "@fortawesome/fontawesome-svg-core";
import { faEnvelope } from "@fortawesome/free-solid-svg-icons";
import { faGithub, faLinkedin } from "@fortawesome/free-brands-svg-icons";
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";

library.add(faGithub, faLinkedin, faEnvelope);

export default {
	components: {
		FontAwesomeIcon
	}
};
</script>

<style scoped>
@font-face {
	font-family: "San Francisco Bold";
	font-style: normal;
	font-weight: 400;
	src: url(https://applesocial.s3.amazonaws.com/assets/styles/fonts/sanfrancisco/sanfranciscodisplay-bold-webfont.eot?#iefix)
			format("embedded-opentype"),
		url(https://applesocial.s3.amazonaws.com/assets/styles/fonts/sanfrancisco/sanfranciscodisplay-bold-webfont.woff2)
			format("woff2"),
		url(https://applesocial.s3.amazonaws.com/assets/styles/fonts/sanfrancisco/sanfranciscodisplay-bold-webfont.woff)
			format("woff"),
		url(https://applesocial.s3.amazonaws.com/assets/styles/fonts/sanfrancisco/sanfranciscodisplay-bold-webfont.ttf)
			format("truetype");
}

.box {
	display: flex;
	align-items: center;
	justify-content: center;
	height: 100%;
	padding: 0px;
	background-color: rgba(0, 0, 0, 0.164);
	color: #fff;
}

.box-work {
	padding: 10px;
	font-size: 18px;
	font-family: "San Francisco Bold";
}

.columns {
	margin-top: 5px;
}
</style>
