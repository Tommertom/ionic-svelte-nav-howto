# HOW-TO Ionic Svelte - Ionic NAV
This repo shows how to implement Ionic Nav in SvelteKit. 

## Why this HowTo
Implementing Ionic Nav requires a bit of deviation from the the Ionic API docs. Not too much, but just a bit.

## Stackblitz
Want to dive into an example? Use the link below to the code-sandbox. After opening the link, please pop-up the render window to see the results.

https://stackblitz.com/github/Tommertom/ionic-svelte-nav-howto


So, you can also clone this repo:
`npx degit https://github.com/Tommertom/ionic-svelte-nav-howto ionic-nav`

## Steps to implement 
Best is just to look at the sample code in route `/nav`
1. The IonNav component is configured in the `+page.svelte`
2. That page imports from `$lib` the NavHome which does the pushing of content (overview->detail)
3. The `NavHome` pushes child/detail views with the props using the `navController` `push` method. It can simply import the component and pass it to the `push` method
4. If need be, you can add `props` to it, which gets passed to the component
5. The child/detail page can implement a `ion-backbutton` for popping the view using the default animation
6. For now, you have to make sure the `ion-backbutton` has a `default-href`, otherwise it won't show

## API info
API for the `+layout.svelte` file:
```
<script lang="ts">
	import IonTabs from './IonTabs.svelte';

	import { videocam, pin } from 'ionicons/icons';
	import { onMount } from 'svelte';

	const myTabs = [
		{
			label: 'Explain',
			icon: pin,
			tab: 'test1'
		},
		{ label: 'Controllers', icon: videocam, tab: 'test2' }
	];

	const logStuff = () => {};
</script>

<IonTabs slot="bottom" tabs={myTabs} ionTabsWillChange={logStuff} ionTabsDidChange={logStuff}
	><slot /></IonTabs
>
```

API for any `+page.svelte` file that has tab-content:

```
<ion-tab tab="test2">
HERE YOUR CONTENT
</ion-tab>
```
Make sure the ion-tab has prop `tab` pointing to the name of the route. So in this case, the route could be `whatever/whenever/tabs/test2`.

## Migration from legacy
See https://github.com/Tommertom/svelte-ionic-npm/blob/main/CHANGELOG.md#05350536