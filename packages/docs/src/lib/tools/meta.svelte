<script lang="ts">
	export let title: string;
</script>

<svelte:head>
	<title>{title}</title>
	<meta name="title" content={title} />
	<meta
		name="description"
		content="Discreet is a SCSS design system created by a Christian ministry of the One Deployment organization."
	/>

	<meta property="og:type" content="website" />
	<meta property="og:url" content="https://discreet.onedeployment.org/" />
	<meta property="og:title" content={title} />
	<meta
		property="og:description"
		content="Discreet is a SCSS design system created by a Christian ministry of the One Deployment organization."
	/>
	<meta property="og:image" content="https://discreet.onedeployment.org/discreet-meta.png" />

	<meta property="twitter:card" content="summary_large_image" />
	<meta property="twitter:url" content="https://discreet.onedeployment.org/" />
	<meta property="twitter:title" content={title} />
	<meta
		property="twitter:description"
		content="Discreet is a SCSS design system created by a Christian ministry of the One Deployment organization."
	/>
	<meta property="twitter:image" content="https://discreet.onedeployment.org/discreet-meta.png" />

	<meta
		name="keywords"
		content="Christian UX design system, Christian programmers, design system for humanitarian organizations, sveltejs design system, scss design system"
	/>
</svelte:head>
