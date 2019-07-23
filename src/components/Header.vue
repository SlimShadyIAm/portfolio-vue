<template>
    <nav class="navbar">
      <div class="container">
        <div class="navbar-brand">
          <router-link class="navbar-item" to="/">
            <span :class="{'has-text-white': $route.name == 'home'}">FAROOQ .</span> <span class="x">X</span><span class="y">Y</span><span class="z">Z</span>
          </router-link>
          <span class="navbar-burger burger" @click="toggleNav" :class="{'is-active': navOpen}" data-target="navbarMenuHeroA">
            <span></span>
            <span></span>
            <span></span>
          </span>
        </div>
        <div id="navbarMenuHeroA" class="navbar-menu" :class="{'is-active': navOpen}">
          <div class="navbar-end">
            <router-link class="navbar-item" :class="{'has-text-white': $route.name == 'home'}" to="/" exact-active-class="is-active">
              Home
            </router-link>
            <router-link class="navbar-item" :class="{'has-text-white': $route.name == 'home'}" to="/work" exact-active-class="is-active">
              Past Work
            </router-link>
          </div>
        </div>
      </div>
    </nav>
</template>

<script>
export default {
  'name': 'header',
  data() {
    return {
      navOpen: false
    }
  },
  methods: {
    toggleNav: function() {
      this.navOpen = !this.navOpen;
    }
  }
}
</script>


<style scoped>
@font-face {
  font-family: "San Francisco Bold";
  font-style: normal;
  font-weight: 400;
  src: url(https://applesocial.s3.amazonaws.com/assets/styles/fonts/sanfrancisco/sanfranciscodisplay-bold-webfont.eot?#iefix) format("embedded-opentype"), url(https://applesocial.s3.amazonaws.com/assets/styles/fonts/sanfrancisco/sanfranciscodisplay-bold-webfont.woff2) format("woff2"), url(https://applesocial.s3.amazonaws.com/assets/styles/fonts/sanfrancisco/sanfranciscodisplay-bold-webfont.woff) format("woff"), url(https://applesocial.s3.amazonaws.com/assets/styles/fonts/sanfrancisco/sanfranciscodisplay-bold-webfont.ttf) format("truetype")
}

.is-active {
  background-color: rgba(0, 0, 0, 0.089) !important;
}

.navbar-brand .navbar-item {
  font-weight: 400;
  font-size: 24px;
  font-family: 'San Francisco Bold'
}

.navbar-brand .navbar-item:hover {
    background-color: rgba(0, 0, 0, 0.089) !important;
}

span.x {
  margin-left: 5px;
  color: red;
}

span.y {
  color: green;
}

span.z {
  color: blue;
}

</style>
