<template>
	<section class="section">
		<WorkObject
			v-for="work in workData"
			:key="work.id"
			:work="work"
			v-on:images="setIndex"
		/>
		<VueGallery
			:images="images"
			:index="index"
			@close="index = null"
		></VueGallery>
	</section>
</template>

<script>
import WorkObject from "@/components/previouswork/WorkObject";
import uuid from "uuid";
import VueGallery from "vue-gallery";

export default {
	name: "WorkObjects",
	components: {
		WorkObject,
		VueGallery
	},
	data() {
		return {
			images: [],
			index: null,
			workData: [
				{
					id: uuid.v4(),
					name: "Runner Assist Dashboard",
					type: "React",
					description: `This project was tasked to us as a final project for the Data & Information course. This site is a dashboard to display data collected from running sensors they developed by a local company. We created the frontend in React, and API and backend in Jeresy and Java servlets.</i>`,
					demo: "",
					source:
						"https://github.com/SlimShadyIAm/runner-assist-frontend/",
					preview: this.importAll(
						require.context(
							"@/assets/img/works/trimm",
							false,
							/\.(png|jpe?g|svg)$/
						)
					)
				},
				{
					id: uuid.v4(),
					name: "EZ-Sign",
					type: "VueJS",
					description: `This web app was created as a high fidelity proof of concept, as a final project for my human-computer interaction course. This is a non-functional prototype.<br>The concept was designed to help sign language users interact with non-sign language users in their daily lives by building a smart sign language translation app by using the camera on your phone.`,
					demo: "https://ezsign.slim.rocks/",
					source: "https://github.com/SlimShadyIAm/ezsign",
					preview: this.importAll(
						require.context(
							"@/assets/img/works/ezsign",
							false,
							/\.(png|jpe?g|svg)$/
						)
					)
				},
				{
					id: uuid.v4(),
					name: "ApexTweaks",
					type: "Jekyll",
					description: `A portfolio/showcase for a developer group that creates popular jailbreak tweaks.`,
					demo: "https://apextweaks.com/",
					// source: "https://github.com/SlimShadyIAm/talkboard-gridsome",
					preview: this.importAll(
						require.context(
							"@/assets/img/works/apex",
							false,
							/\.(png|jpe?g|svg)$/
						)
					)
				},
				{
					id: uuid.v4(),
					name: "TalkBoard",
					type: "Gridsome ~ VueJS",
					description: `A website I created for the host of the TalkBoard podcast, Aaron, a prominent member of the iOS jailbreak community. The podcast invites the most talented developers, from the jailbreaking scene and the general tech industry, for a candid conversation about their passion for their work.`,
					demo: "https://talkboard.live/",
					source: "https://github.com/SlimShadyIAm/talkboard-gridsome",
					preview: this.importAll(
						require.context(
							"@/assets/img/works/talkboard",
							false,
							/\.(png|jpe?g|svg)$/
						)
					)
				},
				{
					id: uuid.v4(),
					name: "AussieJump",
					type: "Game (Electron)",
					description: `This was a game written as a final group project for my Computer Systems course. We used Electron to make the game and an FPGA+accelerometer to add motion controls.<br>Aussie jump is a sidescroller game inspired by Flappy Bird and Google's T-Rex game on Chrome, featuring an Australian theme. Jump to avoid the obstacles. Click the link to watch our demo video!`,
					demo: "https://youtu.be/Kcm_Yac7x3U",
					source: "https://github.com/SlimShadyIAm/AussieJump",
					preview: this.importAll(
						require.context(
							"@/assets/img/works/aussiejump",
							false,
							/\.(png|jpe?g|svg)$/
						)
					)
				},
				{
					id: uuid.v4(),
					name: "Material Admin",
					type: "HTML Template",
					description: `An adminisrative panel template based on the <a href="http://materializecss.com">materializecss.com</a> CSS framework. This template is currently in use as the moderator control panel at <a href="https://opdessertstorm.com">opdessertstorm.com</a>, a game with over <strong>32,000 accounts</strong>. This template was also used in my Runner Assist project, and it was adapted for <a href="https://zira.ovh">Zira's</a> dashboard <a href="https://projects.aamirfarooq.dev/zira/">(demo here</a>, screenshots in gallery).`,
					demo: "https://projects.aamirfarooq.dev/material-admin/",
					source: "https://github.com/SlimShadyIAm/material-admin/",
					preview: this.importAll(
						require.context(
							"@/assets/img/works/material-admin",
							false,
							/\.(png|jpe?g|svg)$/
						)
					)
				},
				// {
				// 	id: uuid.v4(),
				// 	name: "Zira Dashboard",
				// 	type: "HTML template",
				// 	description: `This template, based off of my <a href="https://github.com/SlimShadyIAm/material-admin">Material Admin</a> template, was created as a static HTML mockup for an administrative dashboard for <a href="https://zira.ovh">Zira</a>, a Discord bot with almost <b>10 million users</b> and is in use in 57,000 guilds. The dashboard serves as a graphical way to control the bot&#39;s configuration.`,
				// 	demo: "https://projects.aamirfarooq.dev/zira/",
				// 	source: "https://github.com/SlimShadyIAm/zira-dashboard/",
				// 	preview: this.importAll(
				// 		require.context(
				// 			"@/assets/img/works/zira",
				// 			false,
				// 			/\.(png|jpe?g|svg)$/
				// 		)
				// 	)
				// },
				{
					id: uuid.v4(),
					name: "Froebel's Model UN 2016",
					type: "HTML",
					description: `This website was created to be used as the informational site for the Model UN of Froebel's International School, the high school I attended. A version of this is still being used today: <a href="https://froebels.edu.pk/fromun">froebels.edu.pk/fromun</a>.`,
					demo: "https://projects.aamirfarooq.dev/fromun-site",
					source: "https://github.com/SlimShadyIAm/fromun-site",
					preview: this.importAll(
						require.context(
							"@/assets/img/works/fromun",
							false,
							/\.(png|jpe?g|svg)$/
						)
					)
				},
				{
					id: uuid.v4(),
					name: "This website!",
					type: "VueJS",
					description: `This website was written by me, using the frontend JavaScript framework <a href='https://vuejs.org'>Vue.js</a>, and <a href="https://bulma.io">Bulma</a> as the CSS framework.`,
					demo: "https://aamirfarooq.dev",
					source: "https://github.com/SlimShadyIAm/portfolio-vue/",
					preview: this.importAll(
						require.context(
							"@/assets/img/works/portfolio",
							false,
							/\.(png|jpe?g|svg)$/
						)
					)
				}
				// {
				// 	id: uuid.v4(),
				// 	name: "",
				// 	type: "",
				// 	description: ``,
				// 	demo: "",
				// 	source: "",
				// 	preview: this.importAll(
				// 		require.context(
				// 			"@/assets/img/works/<foldername>",
				// 			false,
				// 			/\.(png|jpe?g|svg)$/
				// 		)
				// 	)
				// },
			]
		};
	},
	methods: {
		importAll: function(r) {
			return r.keys().map(r);
		},
		setIndex(index, imgs) {
			this.index = index;
			this.images = imgs;
		}
	}
};
</script>
