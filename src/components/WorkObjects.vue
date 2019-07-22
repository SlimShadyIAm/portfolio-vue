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
                    "demo": "",
                    "source": "aa",
                    "preview": this.importAll(require.context('@/assets/works/zira', false, /\.(png|jpe?g|svg)$/))
                },
                // {
                //     "id": uuid.v4(),
                //     "name": "Name of project",
                //     "description": "Description here",
                //     "demo": "Link to project demo",
                //     "source": "Link to source code",
                //     "preview": this.importAll(require.context('@/assets/works/<folder name>', false, /\.(png|jpe?g|svg)$/))
                // },
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
