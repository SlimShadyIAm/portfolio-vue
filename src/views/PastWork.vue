<template>
    <div class="work">
        <HeroIntro title="My Previous Work" subtitle="A showcase of my past designs, projects" kind="is-info" />
        <div class="container">
            <WorkObjects />
        </div>
        <Footer />
    </div>
</template>

<script>
    import HeroIntro from '@/components/HeroIntro'
    import WorkObjects from '@/components/WorkObjects'
    import Footer from '@/components/Footer'

export default {
    name: 'PastWork',
    components: {
        HeroIntro, 
        WorkObjects,
        Footer
    }
}
</script>
