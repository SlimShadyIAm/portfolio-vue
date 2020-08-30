<template>
	<footer class="footer">
		<div class="content has-text-centered">
			<p>
				Created by
				<a href="https://github.com/SlimShadyIAm">Aamir Farooq</a>
				&copy; 2020.
			</p>
		</div>
	</footer>
</template>

<script>
export default {
	name: "Footer",
};
</script>

<style scoped>
.footer {
	padding: 10px;
	background-color: hsla(204, 76%, 41%, 1);
	color: #fff;
	font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
		Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
	font-size: 18px;
}
.footer a {
	color: rgb(1, 51, 92);
}
</style>
