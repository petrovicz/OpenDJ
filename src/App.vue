<template>
	<v-app>
		<v-content>
			<router-view />
		</v-content>
	</v-app>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
	name: 'App',
	data: () => ({
		//
	})
});
</script>

<style>
html {
	overflow-y: hidden;
}
</style>
