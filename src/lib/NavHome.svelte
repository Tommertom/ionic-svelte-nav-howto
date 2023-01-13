<script lang="ts">
	import * as allIonicIcons from 'ionicons/icons';
	import NavDetail from './NavDetail.svelte';

	import { navController } from 'ionic-svelte';

	let techs = [
		{
			title: 'Angular',
			icon: 'logoAngular',
			description:
				'A powerful Javascript framework for building single page apps. Angular is open source, and maintained by Google.',
			color: '#E63135'
		},
		{
			title: 'CSS3',
			icon: 'logoCss3',
			description: 'The latest version of cascading stylesheets - the styling language of the web!',
			color: '#0CA9EA'
		},
		{
			title: 'HTML5',
			icon: 'logoHtml5',
			description: "The latest version of the web's markup language.",
			color: '#F46529'
		},
		{
			title: 'JavaScript',
			icon: 'logoJavascript',
			description: 'One of the most popular programming languages on the Web!',
			color: '#FFD439'
		},
		{
			title: 'Sass',
			icon: 'logoSass',
			description:
				'Syntactically Awesome Stylesheets - a mature, stable, and powerful professional grade CSS extension.',
			color: '#CE6296'
		},
		{
			title: 'NodeJS',
			icon: 'logoNodejs',
			description:
				'An open-source, cross-platform runtime environment for developing server-side Web applications.',
			color: '#78BD43'
		},
		{
			title: 'Python',
			icon: 'logoPython',
			description: 'A clear and powerful object-oriented programming language!',
			color: '#3575AC'
		},
		{
			title: 'Markdown',
			icon: 'logoMarkdown',
			description:
				'A super simple way to add formatting like headers, bold, bulleted lists, and so on to plain text.',
			color: '#412159'
		},
		{
			title: 'Tux',
			icon: 'logoTux',
			description: 'The official mascot of the Linux kernel!',
			color: '#000'
		}
	];
	const showDetail = (tech: any) => {
		navController.push(NavDetail, { tech });
	};
</script>

<svelte:head>
	<title>Ionic Companion - Nav</title>
</svelte:head>

<ion-header translucent={true}>
	<ion-toolbar>
		<ion-buttons slot="start">
			<ion-menu-button />
		</ion-buttons>

		<ion-title>Nav element - click on it</ion-title>
	</ion-toolbar>
</ion-header>

<ion-content fullscreen class="ion-padding">
	<ion-list>
		{#each techs as tech}
			<ion-item
				button
				on:keydown={console.log}
				on:click={() => {
					showDetail(tech);
				}}
			>
				<ion-label>
					<h3>{tech.title}</h3>
				</ion-label>
			</ion-item>
		{/each}
	</ion-list>
</ion-content>
