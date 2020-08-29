<template>
	<article class="message is-link">
		<div class="message-header">
			<p>{{ work.name }}</p>
		</div>
		<div class="message-body">
			<div class="columns is-full-on-mobile">
				<div class="column is-5 preview-left">
					<div class="columns">
						<div class="column">
							<figure class="image" v-lazy-container="{ selector: 'img' }">
								<img :data-src="images[0]" alt />
							</figure>
						</div>
					</div>
				</div>
				<div class="column work-body">
					<p class="is-size-5 work-description" v-html="work.description"></p>
					<p class="tool-badges">
						<span v-for="tool in work.tools" :key="tool" class="tool-badge">{{tool}}</span>
					</p>
					<div class="buttons">
						<a class="button is-link" v-on:click="$emit('images', 0, images)" v-if="images.length > 1">
							<font-awesome-icon class="fa" :icon="['fas', 'image']" />Gallery
						</a>
						<a :href="work.demo" class="button is-link" v-if="!work.demo">
							<font-awesome-icon class="fa" :icon="['fas', 'search']" />Demo
						</a>
						<a :href="work.source" class="button is-link" v-if="work.source">
							<font-awesome-icon class="fa" :icon="['fab', 'github']" />GitHub
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
		threshold: 0.1,
	},
});

library.add(faGithub, faSearch, faImage);

export default {
	name: "WorkObject",
	props: ["work"],
	components: {
		FontAwesomeIcon,
	},
	data() {
		return {
			isActive: false,
			images: this.work.preview,
			index: null,
		};
	},
};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Roboto+Mono:wght@500&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Source+Sans+Pro&display=swap");

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
	display: flex;
	justify-content: left;
	margin-top: 10px;
	margin-bottom: 5px;
}

.button {
	margin-left: 5px;
	width: 120px;
	margin-right: 5px;
}

.work-body {
	display: flex;
	flex-direction: column;
}

.work-description {
	flex-grow: 1;
	font-size: 16px;
	margin: 4px 0;
	font-family: "Source Sans Pro", sans-serif;
	color: #222;
}

.message-header {
	font-size: 14px;
	color: #aaa;
	font-family: "Roboto Mono", monospace;
	text-transform: uppercase;
}

.message-body {
	background-color: #fff;
}

.message {
	box-shadow: 0 5px 5px 0 rgba(233, 240, 243, 0.5), 0 0 0 1px #e6ecf8;
	border: 1px solid #e6ecf8;
	border-radius: 5px;
}

.tool-badges {
	line-height: 2em;
	/* margin-top: 10px; */
}

.tool-badge {
	background-color: #3273dc;
	border-radius: 3px;
	padding: 4px 8px;
	color: #fff;
	margin: 0 3px;
	display: inline-block;
	white-space: nowrap;
	font-family: "Roboto Mono", monospace;
	font-size: 12px;
	text-transform: uppercase;
	line-height: 1.5em;
}

@media (max-width: 768px) {
	.button {
		flex: 1 1 0;
		margin-left: 5px;
		margin-right: 5px;
	}

	.buttons {
		margin-bottom: 10px;
		justify-content: center;
	}

	.tool-badges {
		line-height: 2em;
		margin-top: 15px;
	}

	.tool-badge {
		font-size: 13px;
		/* line-height: 2em; */
	}
}
</style>
