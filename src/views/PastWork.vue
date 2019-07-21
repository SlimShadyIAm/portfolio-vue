<template>
    <div class="work">
        <HeroIntro title="My Previous Work" subtitle="A showcase of my past designs, projects" kind="is-info is-bold" />
        <div class="container">
            <WorkObjects />
        </div>
    </div>
</template>

<script>
    import HeroIntro from '@/components/HeroIntro'
    import WorkObjects from '@/components/WorkObjects'

export default {
    name: 'PastWork',
    components: {
        HeroIntro, WorkObjects
    }
}
</script>
