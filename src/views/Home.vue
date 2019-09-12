<template>
	<section style="display: flex; flex-flow: column; height: 100%">
		<DeckSection />
		<LibrarySection />
	</section>
</template>

<script lang="ts">
import Vue from 'vue';
import DeckSection from '@/components/DeckSection.vue';
import LibrarySection from '@/components/LibrarySection.vue';

export default Vue.extend({
	components: {
		DeckSection,
		LibrarySection
	}
});
</script>
