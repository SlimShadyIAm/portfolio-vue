<template>
	<div id="app">
		<Header v-if="$route.name != 'home'"></Header>
		<router-view />
	</div>
</template>

<script>
import "bulma";

import Header from "./components/layout/Header";

export default {
	name: "app",
	components: {
		Header
	}
};
</script>

<style>
</style>
