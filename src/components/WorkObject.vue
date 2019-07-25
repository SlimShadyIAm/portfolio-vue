<template>
	<article class="message is-link">
		<div class="message-header">
			<p>
				{{ work.name }} - <span class="is-italic">{{ work.type }}</span>
			</p>
		</div>
		<div class="message-body">
			<div class="columns is-full-on-mobile">
				<div class="column is-one-third preview-left">
					<div class="columns">
						<div class="column">
							<figure
								class="image"
								v-lazy-container="{ selector: 'img' }"
							>
								<img :data-src="images[0]" alt="" />
							</figure>
						</div>
					</div>
					<div class="columns is-full-on-mobile">
						<div class="column btn-column">
							<a
								class="button is-fullwidth is-link"
								v-on:click="$emit('images', 0, images)"
								>Expand preview</a
							>
						</div>
						<div class="column btn-column">
							<a
								:href="work.demo"
								class="button is-fullwidth is-link"
								:disabled="work.demo === ''"
								>Visit demo</a
							>
						</div>
						<div class="column btn-column">
							<a
								:href="work.source"
								class="button is-fullwidth is-link"
								:disabled="work.source === ''"
							>
								<font-awesome-icon
									class="fa"
									:icon="['fab', 'github']"
								/>
							</a>
						</div>
					</div>
				</div>
				<div class="column is-two-thirds">
					<p class="is-size-5" v-html="work.description"></p>
				</div>
			</div>
		</div>
	</article>
</template>

<script>
import { library } from "@fortawesome/fontawesome-svg-core";
import { faGithub } from "@fortawesome/free-brands-svg-icons";
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";

import LazyLoad from "vue-lazyload";
import Vue from "vue";

var loading = require("@/assets/img/loading.gif");

Vue.use(LazyLoad, {
	observer: true,
	loading: loading,
	// optional
	observerOptions: {
		rootMargin: "0px",
		threshold: 0.1
	}
});

library.add(faGithub);

export default {
	name: "WorkObject",
	props: ["work"],
	components: {
		FontAwesomeIcon
	},
	data() {
		return {
			isActive: false,
			images: this.work.preview,
			index: null
		};
	}
};
</script>

<style scoped>
@media (max-width: 768px) {
	.btn-column {
		padding: 5px;
	}
}

.image img {
	max-height: 0;
	margin: 0 auto;
	overflow: hidden;
}

img[lazy="loading"] {
	width: 50px !important;
	height: 50px !important;
}

img[lazy="loaded"] {
	max-height: 250px;
	width: auto;
	transition: max-height 0.33s ease-out;
}

.preview-left {
	display: flex;
	align-items: center;
	justify-content: center;
	flex-direction: column;
}
</style>
