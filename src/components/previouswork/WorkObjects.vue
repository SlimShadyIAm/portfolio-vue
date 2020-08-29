<template>
	<div>
		<WorkObject
			v-for="work in workData"
			:key="work.id"
			:work="work"
			v-on:images="setIndex"
		/>
		<VueGallery
			:images="images.slice(1, images.length)"
			:index="index"
			@close="index = null"
		></VueGallery>
	</div>
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
					tools: [
						"React",
						"Figma",
						"MaterializeCSS",
						"Jersey",
						"Java servlets"
					],
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
					tools: ["VueJS", "Figma", "Bulma"],
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
					tools: ["Jekyll", "Custom CSS", "Flexbox"],
					description: `A portfolio/showcase for a developer group that creates popular jailbreak tweaks.`,
					demo: "https://apextweaks.com/",
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
					name: "gm!streaks",
					tools: ["Python", "discord.py", "MariaDB"],
					description: `A Snapchat inspired bot for Discord, to send your friends memes and start streaks.\nUsers can send each other "snaps", similar to Snapchat, and each user must send each other one snap within every 24 hour window.\nEach snap adds one point to each user's score, and every day a streak is maintained you get a fire badge.\n\nWatch the demo to learn more!`,
					demo:
						"https://twitter.com/slimshadydev/status/1292915536628678657",
					preview: this.importAll(
						require.context(
							"@/assets/img/works/gmstreaks",
							false,
							/\.(png|jpe?g|svg)$/
						)
					)
				},
				{
					id: uuid.v4(),
					name: "Releasy McReleaseface",
					tools: ["Python", "discord.py", "sqlite3", "RSS feeds"],
					description: `A Discord bot which watches Apple's release feed for new updates to iOS, iPadOS, macOS, watchOS and tvOS.\n\nServer managers have the ability to subscribe to updates from a device and choose a channel for updates to be posted to. Additionally, you can set a role to ping for each OS type, when an update is posted.`,
					demo: "https://slim.rocks/releasy",
					source:
						"https://github.com/SlimShadyIAm/ReleasyMcReleaseface",
					preview: this.importAll(
						require.context(
							"@/assets/img/works/releasy",
							false,
							/\.(png|jpe?g|svg)$/
						)
					)
				},
				{
					id: uuid.v4(),
					name: "TalkBoard",
					tools: ["VueJS", "Gridsome", "Bulma", "Github actions"],
					description: `A website I created for the host of the TalkBoard podcast, Aaron, a prominent member of the iOS jailbreak community. The podcast invites the most talented developers, from the jailbreaking scene and the general tech industry, for a candid conversation about their passion for their work.`,
					demo: "https://talkboard.live/",
					source:
						"https://github.com/SlimShadyIAm/talkboard-gridsome",
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
					tools: [
						"Electron",
						"HTML canvas",
						"Javascript for game",
						"raspberry pi system I/O"
					],
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
					tools: ["Static HTML", "MaterializeCSS"],
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
				{
					id: uuid.v4(),
					name: "Froebel's Model UN 2016",
					tools: ["Static HTML", "Bootstrap"],
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
					tools: ["VueJS", "Bulma"],
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
