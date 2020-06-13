<template>
	<section class="hero home-hero" v-on:>
		<!-- Hero head: will stick at the top -->
		<div class="hero-head">
			<Header />
		</div>
		<div class="hero-body">
			<div class="intro-outer">
				<div class="intro-inner">
					<div class="intro-inner-left">
						<div v-lazy-container="{ selector: 'img' }">
							<img class="responsive-img circle profile-pic" v-bind:data-src="pfp" alt srcset />
						</div>
					</div>
					<div class="intro-inner-right">
						<p class="intro-text">
							<span class="mask">
								AAMIR
								<br />FAROOQ
							</span>
						</p>
						<p class="intro-text-small">Designer. Developer. Dreamer.</p>
						<Contact />
					</div>
				</div>
			</div>
		</div>
	</section>
</template>

<script>
import Header from "@/components/layout/Header";
import Contact from "@/components/home/Contact";
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

export default {
	name: "HeroHome",
	components: {
		Header,
		Contact
	},
	data() {
		return {
			pfp: require("@/assets/img/pfp.jpeg")
		};
	}
};
</script>

<style scoped>
@font-face {
	font-family: "San Francisco Black";
	font-style: normal;
	font-weight: 400;
	src: url(https://applesocial.s3.amazonaws.com/assets/styles/fonts/sanfrancisco/sanfranciscodisplay-black-webfont.eot?#iefix)
			format("embedded-opentype"),
		url(https://applesocial.s3.amazonaws.com/assets/styles/fonts/sanfrancisco/sanfranciscodisplay-black-webfont.woff2)
			format("woff2"),
		url(https://applesocial.s3.amazonaws.com/assets/styles/fonts/sanfrancisco/sanfranciscodisplay-black-webfont.woff)
			format("woff"),
		url(https://applesocial.s3.amazonaws.com/assets/styles/fonts/sanfrancisco/sanfranciscodisplay-black-webfont.ttf)
			format("truetype");
}

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

.home-hero {
	animation: bg-colorfade 30s infinite;
	-moz-animation: bg-colorfade 30s infinite;
	-webkit-animation: bg-colorfade 30s infinite;
}

@keyframes bg-colorfade {
	0% {
		background-color: #7d68dd;
	}

	13.3% {
		background-color: #68a2dd;
	}

	33.3% {
		background-color: #6ce292;
	}

	68% {
		background-color: #6ce292;
	}

	83.3% {
		background-color: #68a2dd;
	}

	100% {
		background-color: #7d68dd;
	}
}

.intro-outer {
	display: flex;
	align-items: center;
	justify-content: center;
	flex-direction: row;
	width: 100%;
}
.intro-inner {
	display: flex;
	align-items: center;
	flex-direction: row;
}

.intro-inner-left,
.intro-inner-right {
	margin: 60px;
}

p.intro-text {
	color: #fff;
	font-size: 48px;
	font-family: "San Francisco Black";
	text-align: right;
	margin: 0;
}

.mask {
	background-image: url("../../assets/img/gradient.jpg");
	background-size: cover;
	background-repeat: no-repeat;
	background-position: center bottom;
	-webkit-background-clip: text;
	background-clip: text;
	color: transparent !important;
	display: inline-block;
	line-height: 1.2em;
}

p.intro-text-small {
	color: #fff;
	font-size: 24px;
	margin: 0;
	font-weight: 400;
	font-family: "San Francisco Bold";
	text-align: right;
}

.profile-pic {
	height: 0;
	border-radius: 50%;
	transition: height 0.33s ease-out;
}

.hero-body {
	padding: 10px;
}

img[lazy="loading"] {
	width: 50px !important;
	height: 50px !important;
}

img[lazy="loaded"] {
	height: 250px;
}

@media (max-width: 768px) {
	.intro-inner {
		flex-direction: column;
		align-items: center;
	}

	.intro-inner-left,
	.intro-inner-right {
		margin: 0;
	}

	/* .intro-text {
        text-align: center !important;
    } */

	.hero-body {
		padding: 20px;
	}
}
</style>

