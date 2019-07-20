<template>
    <div class="column is-one-quarter">
        <div class="box">
            {{ content }}
        </div>
    </div>
</template>

<script>
export default {
    name: 'Tile',
    props: ["content"]
}
</script>


<style scoped>
    @font-face {
        font-family: "San Francisco";
        font-weight: 700;
        src: url("https://applesocial.s3.amazonaws.com/assets/styles/fonts/sanfrancisco/sanfranciscodisplay-black-webfont.woff");
    }
    * {
        text-align: center;
    }
    .box {
        padding: 40px;
        font-size: 24px;
        font-family: 'San Francisco';
        height: 100%;
        display: flex;
        align-items: center;
        justify-content: center;
    }
</style>
