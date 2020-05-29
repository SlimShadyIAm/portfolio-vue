<template>
    <div class="container container-custom">
        <div class="columns yee">
            <AboutColumn :content="whoiam" />
            <AboutColumn :content="whatido" />
        </div>
    </div>
</template>

<script>
import AboutColumn from "@/components/AboutColumn";

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
                subtitle: "Lorem ipsum dolor sit amet, at nam civibus perpetua. Usu enim nominati torquatos cu.",
                featureSets: [
                    {
                        title: "About me",
                        features: ["20 years old", "Pakistani born", "Student at the University of Twente", "2nd year Computer Science BSc", "On track to graduate fall of 2021"]
                    },
                    {
                        title: "Hobbies and interests",
                        features: ["PC building enthusiast", "Hackintoshing and jailbreaking", "Linux and FOSS", "Networking and IoT", "Privacy", "Travelling"]
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
                        features: ["HTML5 and CSS3", "JavaScript", "NodeJS", "Vue.js", "React", "Gridsome", "Gatsby", "Jekyll", "Java", "Python", "Linux and server administration"]
            
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