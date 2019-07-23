<template>
    <section class="section">
        <WorkObject v-for="work in workData" :key="work.id" :work="work" v-on:images="setIndex" />
        <VueGallery :images="images" :index="index" @close="index=null"></VueGallery>
    </section>
</template>

<script>
import WorkObject from '@/components/WorkObject';
import uuid from 'uuid';
import VueGallery from 'vue-gallery';

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
                    "id": uuid.v4(),
                    "name": "Zira Dashboard",
                    "description": `This template, based off of my <a href="https://github.com/SlimShadyIAm/material-admin">Material Admin</a> template, was created as a static HTML mockup for an administrative dashboard for <a href="https://zira.ovh">Zira</a>, a Discord bot with almost <b>10 million users</b> and is in use in 57,000 guilds. The dashboard serves as a graphical way to control the bot&#39;s configuration.`,
                    "demo": "https://projects.farooq.xyz/zira/",
                    "source": "https://github.com/SlimShadyIAm/zira-dashboard/",
                    "preview": this.importAll(require.context('@/assets/img/works/zira', false, /\.(png|jpe?g|svg)$/))
                },
                {
                     "id": uuid.v4(),
                    "name": "Material Admin",
                    "description": `This is a simple template for an administrative panel that is based on the <a href="http://materializecss.com">materializecss.com</a> framework to give the site a beautiful look, adhering to the principles of Google&#39;s Material design language. This template is currently in use as the moderator control panel at <a href="https://opdessertstorm.com">opdessertstorm.com</a>, a game with over <strong>32,000 accounts</strong>.`,
                    "demo": "https://projects.farooq.xyz/material-admin/",
                    "source": "https://github.com/SlimShadyIAm/material-admin/",
                    "preview": this.importAll(require.context('@/assets/img/works/material-admin', false, /\.(png|jpe?g|svg)$/))
                },
                {
                     "id": uuid.v4(),
                    "name": "Interplanetary Banhammer",
                    "description": `Now discontinued, this was a partnership effort initiated several large Discord servers, including r/Google, r/Apple, and several others. The goal was to enhance our moderation outreach by sharing banned users' IDs among other partners, so that we could punish trolls, raiders and spammers to great effect. The estimated outreach was around 100,000 unique Discord users. This site was created to serve as an information hub and disclaimer for users joining servers part of IBH.`,
                    "demo": "https://projects.farooq.xyz/ibh/",
                    "source": "https://github.com/SlimShadyIAm/ibh/",
                    "preview": this.importAll(require.context('@/assets/img/works/ibh', false, /\.(png|jpe?g|svg)$/))
                },
                {
                     "id": uuid.v4(),
                    "name": "Froebel's Model UN 2016",
                    "description": "Yikes",
                    "demo": "https://projects.farooq.xyz/fromun-site",
                    "source": "https://github.com/SlimShadyIAm/fromun-site",
                    "preview": this.importAll(require.context('@/assets/img/works/fromun', false, /\.(png|jpe?g|svg)$/))
                },
                {
                     "id": uuid.v4(),
                    "name": "Toadette",
                    "description": "Yeah haha",
                    "demo": "",
                    "source": "https://github.com/SlimShadyIAm/toadette",
                    "preview": this.importAll(require.context('@/assets/img/works/toadette', false, /\.(png|jpe?g|svg)$/))
                },
                {
                     "id": uuid.v4(),
                    "name": "ChromeOS Updates Bot",
                    "description": "Yeah haha",
                    "demo": "",
                    "source": "https://github.com/SlimShadyIAm/cros-updates",
                    "preview": this.importAll(require.context('@/assets/img/works/cros-updates', false, /\.(png|jpe?g|svg)$/))
                },
                // {
                //     "id": uuid.v4(),
                //     "name": "",
                //     "description": "",
                //     "demo": "",
                //     "source": "",
                //     "preview": this.importAll(require.context('@/assets/img/works/<foler name>', false, /\.(png|jpe?g|svg)$/))
                // },

            ]
        }
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
}
</script>
