<template>
	<v-app>
		<v-app-bar>
			<v-app-bar-title>Challenge</v-app-bar-title>
		</v-app-bar>

		<RouterView :class="{ 'pt-10': Capacitor.isNativePlatform() }" style="margin-top: 96px" />
	</v-app>
</template>

<script setup lang="ts">
	import { Capacitor } from "@capacitor/core";
	import { watch } from "vue";
	import { RouterView, useRoute } from "vue-router";

	const route = useRoute();

	watch(route, () => {
		window.scrollTo({ top: 0, behavior: "smooth" });
	});
</script>

<style>
	html,
	body {
		background: #121212;
	}

	header:not(.book-ctrl) {
		position: fixed;
		width: 100vw;
		z-index: 100;
	}

	@media screen and (max-width: 960px) {
		header:not(.book-ctrl) {
			background-color: #121212;
		}
	}
</style>
