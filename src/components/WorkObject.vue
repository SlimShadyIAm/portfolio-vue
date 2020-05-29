<template>
	<article class="message is-link">
		<div class="message-header">
			<p>
				{{ work.name }} - {{ work.type }}
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
				</div>
				<div class="column is-two-thirds work-body">
					<p class="is-size-5 work-description" v-html="work.description"></p>
					<div class="buttons">
						<a class="button is-fullwidth is-link" v-on:click="$emit('images', 0, images)">
							<font-awesome-icon
								class="fa"
								:icon="['fas', 'image']"
							/> Expand preview</a>
						<a :href="work.demo" class="button is-fullwidth is-link" :disabled="work.demo === ''">
							<font-awesome-icon
								class="fa"
								:icon="['fas', 'search']"
							/> Visit demo</a>
						<a :href="work.source" class="button is-fullwidth is-link" :disabled="work.source === ''">
							<font-awesome-icon
								class="fa"
								:icon="['fab', 'github']"
							/>View GitHub
						</a>
					</div>
				</div>
			</div>
		</div>
	</article>
</template>

<script>
import { library } from "@fortawesome/fontawesome-svg-core";
import { faGithub } from "@fortawesome/free-brands-svg-icons";
import { faSearch } from "@fortawesome/free-solid-svg-icons";
import { faImage } from "@fortawesome/free-solid-svg-icons";
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

library.add(faGithub, faSearch, faImage);

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
@import url('https://fonts.googleapis.com/css2?family=Roboto+Mono:wght@500&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Source+Sans+Pro&display=swap');

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

.fa {
	margin-right: 10px;
}

.buttons {
	margin-top: 20px;
}

.button {
	width: 31%;
	margin-left: 5px;
	margin-right: 5px;}

@media (max-width: 768px) {
	.button {
		width: 100%;
	}
}

.work-body {
	display: flex;
	flex-direction: column;
}

.work-description {
	flex-grow: 1;
	        font-size: 16px;
        margin: 4px 0;
        font-family: 'Source Sans Pro', sans-serif;

}

.message-header {
	font-size: 14px;
	color: #222;
	font-family: 'Roboto Mono', monospace;
	text-transform: uppercase;
}

.message-body {
	background-color: #fff;
}

.message {
	box-shadow: 0 5px 5px 0 rgba(233, 240, 243, 0.5), 0 0 0 1px #E6ECF8;
	border: 1px solid #E6ECF8;
}

</style>
