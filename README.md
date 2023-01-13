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
See code in `+page.svelte`. For the rest, `navController` has the same methods as `ion-nav` - https://ionicframework.com/docs/api/nav


## Todo
Create component for `<ion-nav-link>`