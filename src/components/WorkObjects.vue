<template>
    <section class="section">
        <WorkObject v-for="work in workData" :key="work.id" :work="work" />
    </section>
</template>

<script>
import WorkObject from '@/components/WorkObject';
import uuid from 'uuid';

export default {
    name: "WorkObjects",
    components: {
        WorkObject
    },
    data() {
        return {
            workData: [
                {
                    "id": uuid.v4(),
                    "name": "Zira Dashboard",
                    "description": "Esketiit",
                    "demo": "https://projects.farooq.xyz/zira/",
                    "source": "https://github.com/SlimShadyIAm/zira-dashboard/",
                    "preview": this.importAll(require.context('@/assets/works/zira', false, /\.(png|jpe?g|svg)$/))
                    // "preview": [require('@/assets/works/zira/zira1.png')]
                }
            ]
        }
    }, 
    methods: {
        importAll: function(r) {
            return r.keys().map(r);
        }
    }
}
</script>
