<template>
    <div class="container">
        <div class="columns yee">
            <AboutColumn :content="whoiam" />
            <AboutColumn :content="whoiam" />
            <AboutColumn :content="whoiam" />
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
                subtitle: "I'm a developer!",
                featureTitle: "About me",
                features: ["20 years old", "Pakistani born", "Student at the University of Twente", "2nd year year of computer science BSc", "On track to graduate fall of 2021"]
            }
        }
    }
}
</script>

<style>
    .yee {
        margin-top: -200px;
    }
    .yee:first-child .column:first-child .about-column {
        border-left: 1px solid #E6ECF8;
        border-radius: 10px 0 0 10px;
    }

    .yee:first-child .column:last-child .about-column {
        border-radius:  0 10px 10px 0;
    }
</style>