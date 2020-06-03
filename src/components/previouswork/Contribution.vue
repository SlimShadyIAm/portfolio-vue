<template>
    <div class="column is-6-desktop is-12-tablet">
        <div class="project">
          <img class="project-image" :src="contribution.image">
          <div class="project-body">
            <p class="project-title">{{ contribution.name }}</p>
            <p class="project-desc">{{ contribution.description }}</p>
            <br>
            <div class="buttons">
                <a :href="contribution.url" class="button is-link" :disabled="!contribution.url">
                    <font-awesome-icon
                        class="fa"
                        :icon="['fas', 'search']"
                    /> Demo</a>
            </div>
          </div>
        </div>
    </div>
</template>

<script>
import { library } from "@fortawesome/fontawesome-svg-core";
import { faSearch } from "@fortawesome/free-solid-svg-icons";
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";

library.add(faSearch);

export default {
    name: "Contribution",
    props: ["contribution"],
    components: {
		FontAwesomeIcon
	}
}
</script>

<style scoped>

.project {
    background-color: #fff;
    display: flex;
    width: 100%;
    margin-right: 20px;
    border-radius: 15px;
    margin-bottom: 20px;
    flex: 1 1 auto;
    position: relative;
    box-shadow: 0 5px 5px 0 rgba(233, 240, 243, 0.5), 0 0 0 1px #E6ECF8;
}

.button {
	margin-left: 5px;
	width: 120px;
}

.fa {
	margin-right: 10px;
}

.project-body {
    padding: 20px;
    width: 100%;
    display: flex;
    flex-direction: column;
}

.project-image {
    max-height: 200px;
    border-top-left-radius: 15px;
    border-bottom-left-radius: 15px;
}

.project-title {
    font-weight: 800;
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol";
    font-size: 24px;
    margin-bottom: 5px;
}

.project-desc {
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol";
    flex-grow: 1;
}

@media (max-width: 420px) {
    .project-image {
        max-height: none;
    }
}

@media (max-width: 480px) {
    .project {
        flex-direction: column;
    }
    .project-image {
        width: 100%;
        max-height: none;
        border-top-right-radius: 15px;
        border-bottom-left-radius: 0px;
    }
}
</style>