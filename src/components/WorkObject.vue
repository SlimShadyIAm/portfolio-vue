<template>
    <article class="message is-link">
        <VueGallery :images="images" :index="index" @close="index=null"></VueGallery>
        <div class="message-header">
            <p>{{ work.name }}</p>
        </div>
        <div class="message-body">
            <div class="columns is-full-on-mobile">
                <div class="column is-one-third">
                    <div class="columns">
                        <div class="column">
                            <figure class="image is-2by1">
                                <img :src="images[0]" alt="">
                            </figure>
                        </div>
                    </div>
                    <div class="columns is-full-on-mobile">
                        <div class="column">
                            <a class="button is-fullwidth is-link" @click="index=0">Expand preview</a>
                        </div>
                        <div class="column">
                            <a :href="work.demo" class="button is-fullwidth is-link">Visit demo</a>
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
import VueGallery from 'vue-gallery';

export default {
    name: "WorkObject",
    props: ["work"],
    data () {
        return {
            isActive: false,
            images: this.work.preview,
            index: null
        }
    },
    components: {
        VueGallery
    }
}
</script>
