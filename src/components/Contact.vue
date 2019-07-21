<template>
    <div class="container">
        <article class="message">
            <div class="message-header">
                <p>How to contact me</p>
            </div>
            <div class="message-body">
                <div class="columns">
                    <div class="column">
                        <a href="https://github.com/SlimShadyIAm">
                            <div class="box">
                                <span class="icon is-large">
                                    <font-awesome-icon class="fa-6x" :icon="['fab', 'github']" />
                                </span>
                            </div>
                        </a>
                    </div>
                    <div class="column">
                        <a href="https://www.linkedin.com/in/aamir-farooq-7633a918b">
                            <div class="box">
                                <span class="icon is-large">
                                    <font-awesome-icon class="fa-6x" :icon="['fab', 'linkedin']" />
                                </span>
                            </div>
                        </a>
                    </div>
                    <div class="column">
                        <a href="mailto:aamir@farooq.xyz?">
                            <div class="box">
                                <span class="icon is-large">
                                    <font-awesome-icon class="fa-6x" :icon="['fas', 'envelope']" />
                                </span>
                            </div>
                        </a>
                    </div>                    
                </div>
            </div>
        </article>
    </div>
</template>

<script>
import { library } from '@fortawesome/fontawesome-svg-core';
import { faEnvelope } from '@fortawesome/free-solid-svg-icons';
import { faGithub, faLinkedin } from '@fortawesome/free-brands-svg-icons';
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome';

library.add(faGithub, faLinkedin, faEnvelope);

export default {
    components: {
        FontAwesomeIcon
    }
}
</script>

<style scoped>
    .box {
        display: flex;
        align-items: center;
        justify-content: center;
        height: 100%;
        padding: 40px;
    }
</style>
