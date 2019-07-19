<template>
    <nav class="navbar">
      <div class="container">
        <div class="navbar-brand">
          <router-link class="navbar-item" to="/">
            <span :class="{'has-text-white': $route.name == 'home'}">FAROOQ .</span> <span class="x">X</span><span class="y">Y</span><span class="z">Z</span>
          </router-link>
          <span class="navbar-burger burger" data-target="navbarMenuHeroA">
            <span></span>
            <span></span>
            <span></span>
          </span>
        </div>
        <div id="navbarMenuHeroA" class="navbar-menu">
          <div class="navbar-end">
            <router-link class="navbar-item" to="/" exact-active-class="is-active">
              Home
            </router-link>
            <router-link class="navbar-item" to="/about" exact-active-class="is-active">
              About
            </router-link>
          </div>
        </div>
      </div>
    </nav>
</template>

<style scoped>
@font-face {
  font-family: "San Francisco";
  font-weight: 400;
  src: url("https://applesocial.s3.amazonaws.com/assets/styles/fonts/sanfrancisco/sanfranciscodisplay-bold-webfont.woff");
}

.is-active {
  background-color: rgba(0, 0, 0, 0.089) !important;
}

.navbar-brand .navbar-item {
  font-weight: 400;
  font-size: 24px;
  font-family: 'San Francisco'
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
