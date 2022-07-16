<script>
	import Meta from '$lib/tools/meta.svelte';
</script>

<Meta title="Box - Discreet Christian UX design system" />

<div class="WRAP">
	<h2>Box</h2>
	<div class="box-sm">size sm</div>
	<div class="box-md">size md</div>
	<div class="box-lg">size lg</div>

	<div class="box-lg GROUP-Y">
		<h3>Cookie Compliance</h3>
		<p>
			We use cookies to give you the best possible website experience. By using CodyHouse, you agree
			to our Privacy Policy.
		</p>
		<div class="GROUP">
			<button class="btn-primary">OK, Got it!</button>
			<button class="btn">Close</button>
		</div>
	</div>

	<div class="GROUP">
		<!-- dimensions of 34x34 -->
		<button class="box-lg ICON-SEARCH" aria-label="Search" />
		<button class="box-lg ICON-SORT" aria-label="Sort" />
		<button class="box-lg ICON-WINDOW" aria-label="Window" />
		<button class="box-lg ICON-BOOKMARK" aria-label="Bookmark" />
		<button class="box-lg ICON-LOCK" aria-label="Lock" />
	</div>

	<div class="GROUP">
		<!-- dimensions of 143.44x28 -->
		<span class="box-sm">The letters of Paul</span>
		<span class="box-sm radix-success">The letters of Paul</span>
		<span class="box-sm radix-warning">The letters of Paul</span>
		<span class="box-sm radix-error">The letters of Paul</span>
	</div>
</div>

<style>
	.GROUP-Y {
		display: grid;
		gap: 1rem;
	}
	.GROUP {
		display: flex;
		flex-wrap: wrap;
		gap: 0.5rem;
	}
	.WRAP {
		display: grid;
		gap: 1rem;
	}
	.ICON-SEARCH {
		background: url(/svg/search.svg) no-repeat center/1rem #fff;
	}
	.ICON-SORT {
		background: url(/svg/sort.svg) no-repeat center/1rem #fff;
	}
	.ICON-WINDOW {
		background: url(/svg/window.svg) no-repeat center/1rem #fff;
	}
	.ICON-BOOKMARK {
		background: url(/svg/bookmark.svg) no-repeat center/1rem #fff;
	}
	.ICON-LOCK {
		border-style: dashed;
		background: url(/svg/lock.svg) no-repeat center/1rem #fff;
	}
</style>
