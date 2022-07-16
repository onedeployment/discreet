<script lang="ts">
	import 'discreet/css/all.css';
	import { page } from '$app/stores';
	import { fade } from 'svelte/transition';
	import { introduction_pages, elements_pages } from '$lib/data/navigations';

	let sidebar = false;

	function handledOpen() {
		sidebar = !sidebar;

		// blocks scroll when open
		document.body.className = sidebar ? 'LOCK' : 'UNLOCK';
	}

	$: current_page = $page.url.pathname;
</script>

<header>
	<div class="CONTAINER">
		<div class="CONTENT BETWEEN">
			<a href="/docs" class="PAGE-NAME">Discreet v1.0.0</a>
			<nav class="NAV-HEADER">
				<a
					href="https://www.facebook.com/onedeployment/"
					title="Facebook One Deployment"
					aria-label="Facebook One Deployment"
					rel="noreferrer noopener"
					target="_blank"
				>
					<div class="box-lg ICON-FACEBOOK-F" />
				</a>
				<a
					href="https://github.com/onedeployment/discreet/"
					title="Github One Deployment"
					aria-label="Github One Deployment"
					rel="noreferrer noopener"
					target="_blank"
				>
					<div class="box-lg ICON-GITHUB-ALT" />
				</a>
				<button
					class="box-lg ICON-BOOK-OPEN DESKTOP-HIDDEN"
					title="Open sidebar"
					aria-label="Open sidebar"
					on:click={handledOpen}
				/>
			</nav>
		</div>
	</div>
</header>
<div class="CONTAINER">
	<!-- backdrop to contrast the sidebar -->
	{#if sidebar}
		<div class="BACKDROP" transition:fade on:click={handledOpen} />
	{/if}
	<div class="LAYOUT">
		<aside class:OPENING={!sidebar}>
			<div class="CONTENT SPACE">
				<h3>Guides</h3>
				<nav class="NAV-SIDEBAR SPACE">
					{#each introduction_pages as { name, url }}
						{@const ACTIVE = current_page === url}
						<a href={url} class:ACTIVE>{name}</a>
					{/each}
					<h3>Elements</h3>
					{#each elements_pages as { name, url }}
						{@const ACTIVE = current_page === url}
						<a href={url} class:ACTIVE>{name}</a>
					{/each}
				</nav>
			</div>
		</aside>
		<main>
			<div class="CONTENT">
				<slot />
			</div>
		</main>
	</div>
</div>

<style>
	.SPACE {
		display: grid;
		gap: 0.5rem;
	}
	.NAV-SIDEBAR a {
		padding: 0.25rem 0.5rem;
	}
	.NAV-SIDEBAR a.ACTIVE {
		text-decoration: none;
		border-right: solid 0.125rem #0761d1;
		background: #d3e5ff;
	}
	aside,
	header {
		background: white;
	}
	aside {
		border-right: 0.0625rem solid #eaeaea;
	}
	header {
		border-bottom: 0.0625rem solid #eaeaea;
	}

	.CONTAINER {
		margin-inline: auto;
		max-width: 768px;
	}
	.CONTENT {
		padding: 1rem 2rem;
	}
	.PAGE-NAME {
		font-size: 1.2rem;
		font-weight: bold;
	}
	.NAV-HEADER {
		display: flex;
		gap: 0.5rem;
	}
	.BETWEEN {
		display: flex;
		align-items: center;
		justify-content: space-between;
	}
	@media (min-width: 480px) {
		.DESKTOP-HIDDEN {
			display: none;
		}
		aside {
			top: 0;
			position: sticky;

			/* minimum desktop height */
			min-height: 100vh;

			border-left: 0.0625rem solid #eaeaea;
		}
		.LAYOUT {
			display: grid;
			align-items: start;
			grid-template-columns: 200px 1fr;
		}
	}
	@media (max-width: 480px) {
		.OPENING {
			transform: translateX(-250px);
		}
		.BACKDROP {
			background: rgba(0, 0, 0, 0.15);

			/* backdrop position */
			position: fixed;
			top: 4.1875rem;
			bottom: env(safe-area-inset-bottom);
			right: 0;
			left: 0;
		}
		aside {
			/* For some reason the opacity property interferes with the index. */
			z-index: 1;
			/* size of aside (sidebar) */
			width: 200px;

			/* siderbar position indication */
			position: fixed;
			top: 4.1875rem;
			bottom: env(safe-area-inset-bottom);

			overflow-y: scroll;

			/* iOS scroll behavior rules */
			overscroll-behavior-y: contain;
			-webkit-overflow-scrolling: touch;

			/* .OPENING transition when opening and closing sidebar */
			transition: all 400ms ease-in;
		}
		header {
			top: 0;
			position: sticky;
			z-index: 1;
		}
		:global(.LOCK) {
			height: 100%;
			overflow: hidden;
			touch-action: none;
		}
	}
	.ICON-FACEBOOK-F {
		background: url(/svg/facebook-f.svg) no-repeat center/1rem #fff;
	}
	.ICON-GITHUB-ALT {
		background: url(/svg/github-alt.svg) no-repeat center/1rem #fff;
	}
	.ICON-BOOK-OPEN {
		background: url(/svg/book-open.svg) no-repeat center/1rem #fff;
	}
</style>
