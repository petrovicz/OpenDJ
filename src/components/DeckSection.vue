<template>
	<div id="deckSection">
		<v-row align="center" justify="center" style="height: 100%">
			<v-card class="mx-auto" width="50%">
				<v-toolbar flat dense>
					<v-toolbar-title>
						<span class="subheading">PLAYER</span>
					</v-toolbar-title>
				</v-toolbar>

				<v-card-text>
					<v-row class="mb-4" justify="space-between">
						<v-col class="text-right">
							<v-btn
								@click="load"
								class="ma-2"
								outlined
								fab
								color="green accent-4"
							>
								<v-icon>mdi-upload-multiple</v-icon>
							</v-btn>
							<v-btn
								@click="playPause"
								class="ma-2"
								outlined
								fab
								color="green accent-4"
								:disabled="this.disabled"
							>
								<v-icon>mdi-play-pause</v-icon>
							</v-btn>
						</v-col>
					</v-row>

					<v-slider
						track-color="grey"
						always-dirty
						v-model="volume"
						min="0"
						max="100"
					>
						<template v-slot:prepend>
							<v-icon>
								mdi-volume-medium
							</v-icon>
						</template>

						<template v-slot:append>
							<v-icon>
								mdi-volume-high
							</v-icon>
						</template>
					</v-slider>
				</v-card-text>
			</v-card>
		</v-row>
	</div>
</template>

<script lang="ts">
import Vue from 'vue';
import { ipcRenderer } from 'electron';
const { Howl, Howler } = require('howler');

var audio: any;

export default Vue.extend({
	data: () => ({
		disabled: true,
		volume: 50
	}),
	created() {
		ipcRenderer.on('loadAudioResponse', (event, filePath: string) => {
			if (!filePath) {
				return;
			}

			if (audio) {
				audio.unload();
			}

			audio = new Howl({
				src: filePath,
				html5: true,
				volume: this.volume / 100
			});

			this.disabled = false;
		});
	},
	methods: {
		load() {
			ipcRenderer.send('loadAudio');
		},
		playPause() {
			if (audio.playing()) {
				audio.pause();
			} else {
				audio.play();
			}
		}
	},
	watch: {
		volume: function(val, oldVal) {
			if (!audio) {
				return;
			}

			audio.volume(val / 100);
		}
	}
});
</script>

<style>
#deckSection {
	background: tomato;
	height: 300px;
}
</style>
