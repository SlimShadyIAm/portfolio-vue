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
                    "description": "Esketiit",
                    "demo": "https://projects.farooq.xyz/zira/",
                    "source": "https://github.com/SlimShadyIAm/zira-dashboard/",
                    "preview": this.importAll(require.context('@/assets/works/zira', false, /\.(png|jpe?g|svg)$/))
                },
                {
                     "id": uuid.v4(),
                    "name": "Material Admin",
                    "description": "Whoa",
                    "demo": "https://projects.farooq.xyz/material-admin/",
                    "source": "https://github.com/SlimShadyIAm/material-admin/",
                    "preview": this.importAll(require.context('@/assets/works/material-admin', false, /\.(png|jpe?g|svg)$/))
                },
                {
                     "id": uuid.v4(),
                    "name": "Interplanetary Banhammer",
                    "description": "What's your net worth",
                    "demo": "https://projects.farooq.xyz/ibh/",
                    "source": "https://github.com/SlimShadyIAm/ibh/",
                    "preview": this.importAll(require.context('@/assets/works/ibh', false, /\.(png|jpe?g|svg)$/))
                },
                {
                     "id": uuid.v4(),
                    "name": "Froebel's Model UN 2016",
                    "description": "Yikes",
                    "demo": "https://projects.farooq.xyz/fromun-site",
                    "source": "https://github.com/SlimShadyIAm/fromun-site",
                    "preview": this.importAll(require.context('@/assets/works/fromun', false, /\.(png|jpe?g|svg)$/))
                },
                {
                     "id": uuid.v4(),
                    "name": "Toadette",
                    "description": "Yeah haha",
                    "demo": "",
                    "source": "https://github.com/SlimShadyIAm/toadette",
                    "preview": this.importAll(require.context('@/assets/works/toadette', false, /\.(png|jpe?g|svg)$/))
                },
                {
                     "id": uuid.v4(),
                    "name": "ChromeOS Updates Bot",
                    "description": "Yeah haha",
                    "demo": "",
                    "source": "https://github.com/SlimShadyIAm/cros-updates",
                    "preview": this.importAll(require.context('@/assets/works/cros-updates', false, /\.(png|jpe?g|svg)$/))
                },
                // {
                //     "id": uuid.v4(),
                //     "name": "",
                //     "description": "",
                //     "demo": "",
                //     "source": "",
                //     "preview": this.importAll(require.context('@/assets/works/<foler name>', false, /\.(png|jpe?g|svg)$/))
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
