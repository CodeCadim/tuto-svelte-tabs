<script>
	let pass = "";
	let validLength = false;
	let validCase = false;
	let validSpecial = false;
	let validPass = false;

	function check() {
		validLength = pass.length > 8;
		validCase = pass.toUpperCase() != pass && pass.toLowerCase() != pass;
		validSpecial = pass.replaceAll(/\w/g, "").length > 0;
		validPass = validLength && validCase && validSpecial;
	}
	$: check(pass);
</script>

<fieldset>
	<legend>Choose your password</legend>
	<div class="inputs">
		<input bind:value={pass} type="password" placeholder="..." />
		<button disabled={!validPass} class:valid={validPass} type="button"
			>Enter</button
		>
	</div>
	<div class="validation">
		<div>
			<div class:valid={validLength}>+8</div>
			<span>min 8 chars</span>
		</div>
		<div>
			<div class:valid={validCase}>a..Z</div>
			<span>lower/upper</span>
		</div>
		<div>
			<div class:valid={validSpecial}>~&#</div>
			<span>special</span>
		</div>
	</div>
</fieldset>

<style>
	fieldset {
		max-width: 20rem;
	}
	button,input {
		padding: 0.3rem;
	}
	span {
		font-size: small;
	}
	.valid {
		background-color: var(--Green-600) !important;
		color: var(--Green-200) !important;
	}
	.validation {
		display: flex;
		justify-content: space-between;
		margin: 0.5rem;
	}
	.validation div {
		display: flex;
		flex-direction: column;
		align-items: center;
		width: 4.5rem;
	}
	.validation div div {
		background-color: var(--Gray-900);
		color: var(--Gray-700);
		padding: 0.3rem;
	}
	.validation div span {
		color: gray;
		font-style: italic;
	}
</style>
