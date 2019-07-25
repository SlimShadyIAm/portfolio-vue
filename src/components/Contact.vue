<template>
	<div class="columns">
		<div class="column contact-icon">
			<a href="https://github.com/SlimShadyIAm">
				<div class="box">
					<span class="icon is-large has-text-white">
						<font-awesome-icon
							class="fa-2x"
							:icon="['fab', 'github']"
						/>
					</span>
				</div>
			</a>
		</div>
		<div class="column contact-icon">
			<a href="https://www.linkedin.com/in/farooqaamir">
				<div class="box">
					<span class="icon is-large has-text-white">
						<font-awesome-icon
							class="fa-2x"
							:icon="['fab', 'linkedin']"
						/>
					</span>
				</div>
			</a>
		</div>
		<div class="column contact-icon">
			<a href="mailto:aamir@farooq.xyz?">
				<div class="box">
					<span class="icon is-large has-text-white">
						<font-awesome-icon
							class="fa-2x"
							:icon="['fas', 'envelope']"
						/>
					</span>
				</div>
			</a>
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
.box {
	display: flex;
	align-items: center;
	justify-content: center;
	height: 100%;
	padding: 0px;
	background-color: rgba(0, 0, 0, 0.164);
}
.columns {
	margin-top: 5px;
}
</style>
