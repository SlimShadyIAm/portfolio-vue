<template>
    <section class="hero is-dark is-bold is-fullheight" v-on:>
        <!-- Hero head: will stick at the top -->
        <div class="hero-head">
            <Header />
        </div>
        <div class="hero-body">
            <div class="intro-outer">
                <div class="intro-inner">
                    <div class="intro-inner-left">
                        <img class="responsive-img circle profile-pic"
                            src="https://avatars1.githubusercontent.com/u/10660846?s=460&v=4" alt="" srcset="">
                    </div>
                    <div class="intro-inner-right">
                        <p class="intro-text">
                            AAMIR<br>FAROOQ
                        </p>
                        <p class="intro-text-small">Designer. Developer. Visionary.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
import Header from '@/components/Header';

export default {
    name: 'HeroHome',
    components: {
        Header
    }
}
</script>

<style>
@font-face {
  font-family: "San Francisco";
  font-weight: 700;
  src: url("https://applesocial.s3.amazonaws.com/assets/styles/fonts/sanfrancisco/sanfranciscodisplay-bold-webfont.woff");
}
.intro-outer {
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: row;
    width: 100%;
    animation: bg-colorfade 30s infinite;
    -moz-animation: bg-colorfade 30s infinite;
    -webkit-animation: bg-colorfade 30s infinite;
}
.intro-inner {
    display: flex;
    align-items: center;
    flex-direction: row;
}

.intro-inner-left,
.intro-inner-right {
    margin: 60px;
}

p.intro-text {
    color: #fff;
    font-size: 48px;
    font-family: 'San Francisco';
    text-align: right;
    margin: 0;
}

p.intro-text-small {
    color: #fff;
    font-size: 24px;
    margin: 0;
    font-family: 'San Francisco';
}

</style>

