<template>
	<section class="section">
		<WorkObject v-for="work in workData" :key="work.id" :work="work" v-on:images="setIndex" />
		<VueGallery :images="images" :index="index" @close="index = null"></VueGallery>
	</section>
</template>

<script>
import WorkObject from "@/components/WorkObject";
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
					type: "Website (ReactJS)",
					description: `This project was tasked to us by the University of Twente as a final project for the first year. We were working alongside TRIMM, the client, who had developed sensors for runners to wear which would track their running performance on things like liftoff distance, lower leg impact, push-off force, and several other metrics.<br>Our task was to make sense of the large amounts of data we were given, analyse it and display it in a web dashboard such that a potential customer could view their running performance, see what they need to improve and what they are doing well. The ultimate goal was to generate useful feedback on how runners could improve.<br>We created the frontend, the backend and API (a Java project in a separate private repository), as well as the database structure. Sample data to populate the database was provided to us.<br><i>Unfortunately a demo is unavailable as the database we used was hosted on university servers, which have since been wiped for the next years' projects</i>`,
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
					name: "AussieJump",
					type: "Game (Electron)",
					description: `This was a game written as a final group project for the 5th module at the Unviersity of Twente.<br>Aussie jump is a sidescroller game inspired by Flappy Bird and Google's T-Rex game on Chrome. It features an Australian theme, as the character you control is a kangaroo and you avoid cactuses which come at you from two sides at varying speeds. Use your arrow keys, or tilt the sensor to avoid the obstacles and get the highest score you can. Boing! Boing! Boing!<br />The game is written in Electron v6.1.2 and makes use of the <code>onoff</code> NPM package to support communication over GPIO with an FPGA, which is connected to an accelerometer. This gives the user the choice to control the game with a keyboard or motion controls.<br><i>A demo video is available <a href="https://youtu.be/Kcm_Yac7x3U">here</a>, and you can play yourself if you clone the repository and run it yourself, however it will run super fast as it was designed to be run on a Raspberry Pi which is much slower. You can't use motion controls without our hardware setup (FPGA+accelerometer)</i>`,
					demo: "https://youtu.be/Kcm_Yac7x3U",
					source: "https://github.com/SlimShadyIAm/runner-assist-frontend/AussieJump",
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
					name: "Zira Dashboard",
					type: "Website",
					description: `This template, based off of my <a href="https://github.com/SlimShadyIAm/material-admin">Material Admin</a> template, was created as a static HTML mockup for an administrative dashboard for <a href="https://zira.ovh">Zira</a>, a Discord bot with almost <b>10 million users</b> and is in use in 57,000 guilds. The dashboard serves as a graphical way to control the bot&#39;s configuration.`,
					demo: "https://projects.aamirfarooq.dev/zira/",
					source: "https://github.com/SlimShadyIAm/zira-dashboard/",
					preview: this.importAll(
						require.context(
							"@/assets/img/works/zira",
							false,
							/\.(png|jpe?g|svg)$/
						)
					)
				},
				{
					id: uuid.v4(),
					name: "Material Admin",
					type: "Website",
					description: `This is a simple template for an administrative panel that is based on the <a href="http://materializecss.com">materializecss.com</a> framework to give the site a beautiful look, adhering to the principles of Google&#39;s Material design language. This template is currently in use as the moderator control panel at <a href="https://opdessertstorm.com">opdessertstorm.com</a>, a game with over <strong>32,000 accounts</strong>.`,
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
					type: "Website",
					description: `This website was created to be used as the official site for the Model UN of Froebel's International School, the high school I attended. Here, students were able to find information regarding the host team staff, scheduling as well as how to register to participate. The final version, tweaked by Rockville, can be found at <a href="https://froebels.edu.pk/fromun">froebels.edu.pk/fromun.</a>, though it has since been modified by students to reflect information from newer years.`,
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
					name: "Taggy McTagface",
					type: "Discord bot (NodeJS)",
					description: "This bot was created for the <a href='https://discord.gg/chromeos'>r/ChromeOS Discord server</a>.<br>It provides various utilities useful for regular members, such as the ability to add custom text snippets to the database so that when you invoke a command, it will post that snippet. This is very useful, for example in the context of support, when you want to post a series of common Linux commands; you wouldn't have to type them out by hand, rather just type something like <code>$ubuntu</code> and the bot would post the pre-saved response.<br>Another key feature is that it makes use of a <a href='https://cros-updates.netlify.com/'>ChromeOS update release API</a>, so you can check which version and platform number a device model is on; useful for seeing how device updates are rolled out to all models.",
					demo: "https://discord.gg/chromeos",
					source: "https://github.com/SlimShadyIAm/taggymctagface",
					preview: this.importAll(
						require.context(
							"@/assets/img/works/taggymctagface",
							false,
							/\.(png|jpe?g|svg)$/
						)
					)
				},
								{
					id: uuid.v4(),
					name: "Toadette",
					type: "Discord bot",
					description:
						"Did you know that Mario Kart has a competitive scene? I know, I'm as surprised as you are.<br>I made this bot for a friend's Mario Kart 8 team Discord as he wanted a simple way for his team to communicate to each other when there was a scrimmage match available for the team to compete in, and for the team members to mark themselves as available. You can use the command <code>!start</code> to notify the server that a war is starting, and teammates can join the lineup by typing <code>!can</code>. It's that easy.",
					demo: "",
					source: "https://github.com/SlimShadyIAm/toadette",
					preview: this.importAll(
						require.context(
							"@/assets/img/works/toadette",
							false,
							/\.(png|jpe?g|svg)$/
						)
					)
				},
								{
					id: uuid.v4(),
					name: "Interplanetary Banhammer",
					type: "Website",
					description: `Now discontinued, this was a partnership effort initiated several large Discord servers, including r/Google, r/Apple, and several others. The goal was to enhance our moderation outreach by sharing banned users' IDs among other partners, so that we could punish trolls, raiders and spammers to great effect. The estimated outreach was around 100,000 unique Discord users. This site was created to serve as an information hub and disclaimer for users joining servers part of IBH.`,
					demo: "https://projects.aamirfarooq.dev/ibh/",
					source: "https://github.com/SlimShadyIAm/ibh/",
					preview: this.importAll(
						require.context(
							"@/assets/img/works/ibh",
							false,
							/\.(png|jpe?g|svg)$/
						)
					)
				},
				{
					id: uuid.v4(),
					name: "ChromeOS Updates Bot",
					type: "Discord bot (NodeJS)",
					description: "This bot was created for the <a href='https://discord.gg/chromeos'>r/ChromeOS Discord server</a>.<br>It posts a notification in the server when a new update is released for ChromeOS, the operating system that runs on Chromebooks",
					demo: "https://discord.gg/chromeos",
					source: "https://github.com/SlimShadyIAm/cros-updates",
					preview: this.importAll(
						require.context(
							"@/assets/img/works/cros-updates",
							false,
							/\.(png|jpe?g|svg)$/
						)
					)
				}
				// {
				//     "id": uuid.v4(),
				//     "name": "",
				//     "description": "",
				//     "demo": "",
				//     "source": "",
				//     "preview": this.importAll(require.context('@/assets/img/works/<foler name>', false, /\.(png|jpe?g|svg)$/))
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
