<script lang="ts">
	import * as allIonicIcons from 'ionicons/icons';
	export let tech: any;
</script>

<ion-header translucent>
	<ion-toolbar>
		<ion-buttons slot="start">
			<ion-back-button text="Back off!" default-href="/" color="danger" />
		</ion-buttons>
		<ion-title>{tech.title}</ion-title>
	</ion-toolbar>
</ion-header>
<ion-content fullscreen class="ion-padding">
	<p>{tech.description}</p>
</ion-content>
