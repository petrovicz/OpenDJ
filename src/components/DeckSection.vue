<template>
	<div id="deckSection">
		<v-row align="center" justify="center" style="height: 100%">
			<v-card class="pa-6" outlined tile>
				Deck section
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
#deckSection {
	background: tomato;
	height: 300px;
}
</style>
