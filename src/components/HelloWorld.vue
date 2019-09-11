<template>
	<v-container>
		<v-layout text-center wrap>
			<v-flex xs12>
				<v-img
					:src="require('../assets/vinyl.png')"
					class="my-3"
					contain
					height="200"
				></v-img>
			</v-flex>

			<v-flex xs12 class="ma-10">
				<h1 class="display-2 font-weight-bold mb-3">
					Welcome to OpenDJ
				</h1>
				<p class="subheading font-weight-regular">
					For help and collaboration with other OpenDJ developers,
					<br />
					visit the
					<a
						href="https://github.com/petrovicz/OpenDJ"
						target="_blank"
					>
						GitHub</a
					>
					page
				</p>
			</v-flex>

			<v-flex xs12>
				<div class="my-12"></div>
			</v-flex>

			<v-flex xs12>
				<h2 class="headline font-weight-bold mb-3">More info</h2>
				<p class="subheading font-weight-regular">
					This is a pre-alpha version of OpenDJ.
					<br />
					Because of that, it's not eligible for any kind of DJing
					yet.
					<br />
					You can get info about upcoming releases on the
					<a
						href="https://github.com/petrovicz/OpenDJ"
						target="_blank"
					>
						GitHub</a
					>
					page
				</p>
			</v-flex>
		</v-layout>
	</v-container>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
	data: () => ({})
});
</script>
