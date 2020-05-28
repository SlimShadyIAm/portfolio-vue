<template>
  <div class="column">
      <div class="about-column">
            <font-awesome-icon class="fa-3x column-icon" :icon="['far', 'user']" />
            <br>
            <p class="column-title">{{ content.title }}</p>
            <p class="column-subtitle">{{ content.subtitle }}</p>
            <p class="column-feature-title">{{ content.featureTitle }}</p>
            <p class="column-feature" v-for="feature in content.features" :key="feature">{{ feature }}</p>
      </div>
  </div>
</template>

<script>
import { library } from "@fortawesome/fontawesome-svg-core";
import {
	faUser
} from "@fortawesome/free-regular-svg-icons";
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";

library.add(faUser);

export default {
    name: "About Column",
    props: ["content"],
    components: {
		FontAwesomeIcon
	}
}
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Roboto+Mono:wght@700&display=swap');
    .about-column {
        width: 100%;
        padding: 50px;
        background-color: #fff;
        border-bottom: 1px solid #E6ECF8;
        border-right: 1px solid #E6ECF8;
        text-align: center;
    }

    .column {
        padding: 0;
    }

    .column-icon {
        margin-bottom: 20px;
        color: rgb(177, 92, 226);
    }
    .column-title {
        font-size: 18px;
        color: #555;
        font-family: 'Roboto Mono', monospace;
        text-transform: uppercase;
    }
    .column-subtitle {
        margin-top: 30px;
    }
    .column-feature-title {
        font-size: 14px;
        color: rgb(141, 23, 209);
        font-family: 'Roboto Mono', monospace;
        text-transform: uppercase;
        margin-top: 30px;
        margin-bottom: 30px;
    }
    .column-feature {
        font-size: 14px;
        color: #444;
        margin: 4px 0;
    }

</style>