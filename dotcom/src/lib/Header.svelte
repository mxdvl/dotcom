<script lang="ts">
	import type { Lang } from "./lang";

	export let lang: Lang;
</script>

<svelte:head>
	<html {lang} />
</svelte:head>

<header class="header wrap wide" role="banner">
	<nav>
		<ul>
			<li class="home active">
				<a class="branding" href={lang == "fr" ? "/allo" : "/hi"} rel="home">
					<svg version="1.1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 36 36" xml:space="preserve">
						<g id="cmps" fill="none" stroke-width="2">
							<line x1="18" y1="0" x2="18" y2="36" />
							<line x1="18" y1="18" x2="36" y2="18" />
							<circle cx="18" cy="18" r="12" /></g
						>
					</svg>
				</a>
			</li>

			<li class="menu-item ">
				{#if lang == "en"}
					<a href="/works">Works</a>
				{:else if lang == "fr"}
					<a href="/travaux">Travaux</a>
				{:else}
					No dice
				{/if}
			</li>

			<li class="menu-item ">
				{#if lang == "en"}
					<a href="/profile">Profile</a>
				{:else if lang == "fr"}
					<a href="/profil">Profil</a>
				{:else}
					waddup/error
				{/if}
			</li>

			<li class="menu-item" lang="fr">
				<a href="/allo">allô</a>
				<span class="padded">–</span>
				<a href="/hi">hi</a>
			</li>
		</ul>
	</nav>
</header>

<style>
	svg {
		stroke: currentColor;
		height: 2.25rem;
	}

	ul {
		display: flex;
		justify-content: space-between;

		list-style-type: none;
		margin: 0;
		padding: 0;
		font-weight: 480;
	}

	li {
		height: 2.25rem;
		display: flex;
		text-transform: uppercase;
		align-items: center;
	}

	.padded {
		padding: 0 0.5rem;
	}

	a {
		display: block;
		margin: auto;
		background: none;
	}
</style>
