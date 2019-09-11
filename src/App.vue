<template>
	<v-app>
		<SystemBar />

		<v-content>
			<router-view />
		</v-content>
	</v-app>
</template>

<script lang="ts">
import Vue from 'vue';
import SystemBar from '@/components/SystemBar.vue';

export default Vue.extend({
	name: 'App',
	components: {
		SystemBar
	},
	data: () => ({
		//
	})
});
</script>

<style>
::-webkit-scrollbar {
	display: none;
}
</style>
