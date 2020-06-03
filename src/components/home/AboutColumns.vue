<template>
    <div class="container container-custom">
        <div class="columns yee">
            <AboutColumn :content="whoiam" />
            <AboutColumn :content="whatido" />
        </div>
    </div>
</template>

<script>
import AboutColumn from "@/components/home/AboutColumn";

export default {
    name: "About Columns",
    components: {
        AboutColumn
    },
    data() {
		return {
            whoiam: {
                title: "Who I Am",
                icon: "user",
                iconType: "far",
                subtitle: "I'm an enthusiastic and passionate worker. I love building meaningful relationships when working with people.",
                featureSets: [
                    {
                        title: "About me",
                        features: ["20 years old", "Pakistani born", "Student at the University of Twente", "2nd year Computer Science BSc", "On track to graduate fall of 2021"]
                    },
                    {
                        title: "Hobbies and interests",
                        features: ["PC building enthusiast", "Hackintoshing and jailbreaking", "Online community management", "Privacy and security", "Podcasts and reading", "Travelling", "Cooking"]
                    }
                ]
            },
            whatido: {
                title: "What I Do",
                icon: "laptop-code",
                iconType: "fas",
                subtitle: "My primary focus is on frontend design and development. I enjoy making beautiful, responsive and fast websites.",
                featureSets: [
                    {
                        title: "My Tools",
                        features: ["HTML5 and CSS3", "JavaScript", "NodeJS", "Figma", "Vue.js", "React", "Gridsome", "Gatsby", "Jekyll", "Java", "Python", "Linux and server administration"]
            
                    }
                ]
            }
        }
    }
}
</script>

<style scoped>
    .yee {
        margin-top: -275px;
    }
    .yee:first-child .column:first-child .about-column {
        border-left: 1px solid #E6ECF8;
        border-radius: 10px 0 0 10px;
    }

    .yee:first-child .column:last-child .about-column {
        border-radius:  0 10px 10px 0;
    }
    @media screen and (min-width: 1408px) {
        .container {
            max-width: 1000px;
        }
    }
    @media screen and (min-width: 1216px) {
        .container {
            max-width: 1000px;
        }
    }
</style>