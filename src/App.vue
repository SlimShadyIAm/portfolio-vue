<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<script>
import bulma from 'bulma';

import Header from './components/Header'

export default {
  name: 'app',
  components: {
    Header
  }
}
</script>


<style>

</style>
