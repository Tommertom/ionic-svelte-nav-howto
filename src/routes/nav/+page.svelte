<script lang="ts">
	import NavHome from '$lib/NavHome.svelte';
	import { IonNav } from 'ionic-svelte';
</script>

<svelte:head>
	<title>Ionic Companion - Nav</title>
</svelte:head>

<IonNav root={NavHome} />
