<script>
	import Meta from '$lib/tools/meta.svelte';
</script>

<Meta title="Input - Discreet Christian UX design system" />

<div class="WRAP">
	<h2>Input</h2>

	<label for="r1">He is Mark ...</label>
	<input type="text" name="r1" id="r1" placeholder="He is Mark ..." />

	<label for="r2">Choose a book</label>
	<select name="r2" id="r2">
		<option value="Mark">Mark</option>
		<option value="John">John</option>
		<option value="Peter">Peter</option>
		<option value="Peter">Luke</option>
	</select>

	<label for="r3">Say hello to Peter</label>
	<textarea name="r3" id="r3" rows="10" placeholder="Hello Peter ..." />

	<label for="r4">Choose a book</label>
	<select name="r4" id="r4" size="3">
		<option value="Mark">Mark</option>
		<option value="John" selected>John</option>
		<option value="Peter">Peter</option>
		<option value="Luke">Luke</option>
	</select>

	<label for="r5">Choose an amount</label>
	<input
		type="number"
		name="r5"
		id="r5"
		step="1"
		inputmode="numeric"
		placeholder="0.00"
		class="ICON-DOLLAR-SIGN-ALT"
	/>

	<div>
		<input type="checkbox" name="r6" id="r6" checked />
		<label for="r6">I agree to continue writing a message</label>
	</div>

	<div>
		<input type="radio" id="Peter" name="r7" value="Peter" checked />
		<label for="Peter">Peter</label>
	</div>

	<div>
		<input type="radio" id="Maark" name="r7" value="Maark" />
		<label for="Maark">Mark</label>
	</div>

	<div>
		<input type="radio" id="Luke" name="r7" value="Luke" />
		<label for="Luke">Luke</label>
	</div>

	<label for="r8">Choose your browser from the list:</label>
	<input list="browsers" id="r8" />
	<datalist id="browsers">
		<option value="Edge" />
		<option value="Firefox" />
		<option value="Chrome" />
		<option value="Opera" />
		<option value="Safari" />
	</datalist>

	<label for="r9">Choose a date</label>
	<input type="date" id="r9" value="2018-07-22" min="2018-01-01" max="2018-12-31" />

	<label for="r10">Choose a date and time</label>
	<input type="datetime-local" id="r10" value="2016-06-23T09:07" />

	<label for="r11">Your friend's email</label>
	<input type="email" id="r11" placeholder="peter@example.com" class="ICON-ENVELOPE" multiple />

	<label for="r12">In what month and year was Peter born</label>
	<input type="month" id="r12" min="2018-03" value="2018-05" />

	<label for="r13">Here a password ...</label>
	<input
		type="password"
		id="r13"
		autocomplete="new-password"
		placeholder="Lemon cake"
		class="ICON-LOCK"
	/>

	<label for="r14">Find a book ...</label>
	<input type="search" id="r14" placeholder="Find a book ..." class="ICON-SEARCH" />

	<div>
		<label for="r15">Choose more books</label>
		<select name="r15" id="r15">
			<option value="Mark">Mark</option>
			<option value="John">John</option>
			<option value="Peter">Peter</option>
			<option value="Peter">Luke</option>
		</select>
	</div>

	<label for="r16">Write any phone number</label>
	<input type="tel" id="r16" autocomplete="tel" placeholder="757-864-5036" class="ICON-PHONE" />

	<label for="r17">Input disabled</label>
	<input type="text" id="r17" placeholder="Input disabled" disabled />

	<label for="r18">Time now</label>
	<input type="time" id="r18" min="09:00" max="18:00" value="18:02" />

	<label for="r19">Favorite website</label>
	<input type="url" id="r19" placeholder="https://www.bible.com/en" class="ICON-LINK-H" />

	<label for="r20">Text type message ...</label>
	<input type="text" id="r20" placeholder="Text type message ..." />

	<label for="r21">Other favorite website</label>
	<input type="url" id="r21" placeholder="https://www.bible.com/en" class="ICON-LOADING" disabled />

	<input type="button" value="Give now" class="btn" />
	<input type="button" value="Give now" class="btn-primary" />
	<input type="button" value="Give now" class="btn" disabled />
	<button class="btn">Give tomorrow</button>
	<div>
		<input type="button" value="Upload all files" class="ICON-LOADING" disabled />
	</div>
</div>

<style>
	.WRAP {
		display: grid;
		gap: 1rem;
	}
	.ICON-DOLLAR-SIGN-ALT {
		padding-left: 2.35rem;
		background: url(/svg/dollar-sign-alt.svg) no-repeat center left 0.75rem/1em #fff;
	}
	.ICON-ENVELOPE {
		padding-left: 2.35rem;
		background: url(/svg/envelope.svg) no-repeat center left 0.75rem/1em #fff;
	}
	.ICON-SEARCH {
		padding-left: 2.35rem;
		background: url(/svg/search.svg) no-repeat center left 0.75rem/1em #fff;
	}
	.ICON-LOCK {
		padding-left: 2.35rem;
		background: url(/svg/lock.svg) no-repeat center left 0.75rem/1em #fff;
	}
	.ICON-PHONE {
		padding-left: 2.35rem;
		background: url(/svg/phone.svg) no-repeat center left 0.75rem/1em #fff;
	}
	.ICON-LINK-H {
		padding-left: 2.35rem;
		background: url(/svg/link-h.svg) no-repeat center left 0.75rem/1em #fff;
	}
	.ICON-LOADING {
		padding-left: 2.35rem;
		background: url(/animation/loading.gif) no-repeat center left 0.75rem/1em #fff;
	}
</style>
