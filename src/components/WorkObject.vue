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
                            <figure class="image is-2by1">
                                <img :src="work.preview" alt="">
                            </figure>
                        </div>
                    </div>
                    <div class="columns is-full-on-mobile">
                        <div class="column">
                            <router-link to="#" class="button is-fullwidth is-link">Expand preview</router-link>
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
export default {
    name: "WorkObject",
    props: ["work"]
}
</script>
