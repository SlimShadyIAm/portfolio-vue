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
    font-family: "San Francisco Black";
    font-style: normal;
    font-weight: 400;
    src: url(https://applesocial.s3.amazonaws.com/assets/styles/fonts/sanfrancisco/sanfranciscodisplay-black-webfont.eot?#iefix) format("embedded-opentype"), url(https://applesocial.s3.amazonaws.com/assets/styles/fonts/sanfrancisco/sanfranciscodisplay-black-webfont.woff2) format("woff2"), url(https://applesocial.s3.amazonaws.com/assets/styles/fonts/sanfrancisco/sanfranciscodisplay-black-webfont.woff) format("woff"), url(https://applesocial.s3.amazonaws.com/assets/styles/fonts/sanfrancisco/sanfranciscodisplay-black-webfont.ttf) format("truetype")
    }

    * {
        text-align: center;
    }
    .box {
        padding: 40px;
        font-size: 24px;
        font-family: 'San Francisco Bold';
        height: 100%;
        display: flex;
        align-items: center;
        justify-content: center;
    }
</style>
