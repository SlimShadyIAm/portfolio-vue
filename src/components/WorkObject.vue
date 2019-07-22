<template>
    <article class="message is-link">
        <div class="message-header">
            <p>{{ work.name }}</p>
        </div>
        <div class="message-body">
            <div class="columns is-full-on-mobile">
                <div class="column is-one-third">
                    <div class="columns">
                        <div class="column">
                            <figure class="image">
                                <img :src="images[0]" alt="">
                            </figure>
                        </div>
                    </div>
                    <div class="columns is-full-on-mobile">
                        <div class="column btn-column">
                            <a class="button is-fullwidth is-link" v-on:click="$emit('images', 0, images)">Expand preview</a>
                        </div>
                        <div class="column btn-column">
                            <a :href="work.demo" class="button is-fullwidth is-link" :disabled="work.demo === ''">Visit demo</a>
                        </div>
                        <div class="column btn-column">
                            <a :href="work.source" class="button is-fullwidth is-link" :disabled="work.source === ''">
                                <font-awesome-icon class="fa" :icon="['fab', 'github']" />
                            </a>
                        </div>
                    </div>
                </div>
                <div class="column is-two-thirds">
                    {{ work.description }}
                </div>
            </div>
        </div>
    </article>
</template>

<script>
import { library } from '@fortawesome/fontawesome-svg-core';
import { faGithub } from '@fortawesome/free-brands-svg-icons';
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome';

library.add(faGithub);

export default {
    name: "WorkObject",
    props: ["work"],
    components: {
        FontAwesomeIcon
    },
    data () {
        return {
            isActive: false,
            images: this.work.preview,
            index: null
        }
    },
    
}
</script>

<style scoped>
   @media (max-width: 768px) {
        .btn-column {
            padding: 5px
        }
   }

   .image img {
       max-height: 250px;
       width: auto;
       margin: 0 auto;
   }
</style>
