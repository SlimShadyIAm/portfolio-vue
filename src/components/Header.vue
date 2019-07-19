<template>
    <nav class="navbar">
      <div class="container">
        <div class="navbar-brand">
          <a class="navbar-item">
            <!-- <img src="https://bulma.io/images/bulma-type-white.png" alt="Logo"> -->
          </a>
          <span class="navbar-burger burger" data-target="navbarMenuHeroA">
            <span></span>
            <span></span>
            <span></span>
          </span>
        </div>
        <div id="navbarMenuHeroA" class="navbar-menu">
          <div class="navbar-end">
            <router-link class="navbar-item" to="/" active-class="is-active">
              Home
            </router-link>
            <router-link class="navbar-item" to="/about" active-class="is-active">
              About
            </router-link>
          </div>
        </div>
      </div>
    </nav>
</template>
