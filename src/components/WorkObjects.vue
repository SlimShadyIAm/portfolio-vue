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
                    "demo": "https://zira.slim.ovh",
                    "preview": require('@/assets/works/zira.png')
                }
            ]
        }
    }
}
</script>
