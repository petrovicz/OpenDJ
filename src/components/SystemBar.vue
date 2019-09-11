<template>
	<v-system-bar app window style="-webkit-app-region: drag;" class="pr-0">
		<v-icon>mdi-disc</v-icon>
		<span>OpenDJ</span>
		<div class="flex-grow-1"></div>

		<v-btn
			tile
			icon
			style="-webkit-app-region: no-drag"
			:height="buttonHeight"
			:width="buttonWidth"
			@click="minimize()"
		>
			<v-icon class="ma-0">mdi-minus</v-icon>
		</v-btn>
		<v-btn
			tile
			icon
			style="-webkit-app-region: no-drag"
			:height="buttonHeight"
			:width="buttonWidth"
			@click="maximize()"
		>
			<v-icon class="ma-0">mdi-checkbox-blank-outline</v-icon>
		</v-btn>
		<v-btn
			tile
			icon
			style="-webkit-app-region: no-drag"
			:height="buttonHeight"
			:width="buttonWidth"
			@click="quit()"
		>
			<v-icon class="ma-0">mdi-close</v-icon>
		</v-btn>
	</v-system-bar>
</template>

<script lang="ts">
import Vue from 'vue';

const { remote, ipcRenderer } = require('electron');

export default Vue.extend({
	data: () => ({
		buttonHeight: 32,
		buttonWidth: 45
	}),
	methods: {
		minimize() {
			remote.getCurrentWindow().minimize();
		},
		maximize() {
			const currentWindow = remote.getCurrentWindow();

			if (currentWindow.isMaximized()) {
				currentWindow.unmaximize();
			} else {
				currentWindow.maximize();
			}
		},
		quit() {
			remote.app.quit();
		}
	}
});
</script>
