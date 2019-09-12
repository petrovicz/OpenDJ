<template>
	<div id="librarySection">
		<v-row align="center" justify="center" style="height: 100%">
			<v-card class="pa-6" outlined tile>
				Library section
			</v-card>
		</v-row>
	</div>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
	data: () => ({})
});
</script>

<style>
#librarySection {
	background: gold;
	flex: 1 1 auto;
	overflow: auto;
}
</style>
