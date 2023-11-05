<script>
	let firstname = "John";
	let lastname = "Doe";
</script>
<fieldset>
	<legend>Change identity</legend>
	<div class="inputs">
		<label for="firstname">First name</label>
		<input bind:value={firstname} type="text" id="firstname" />
	</div>
	<div class="inputs">
		<label for="lastname">Last name</label>
		<input bind:value={lastname} type="text" id="lastname" />
	</div>
	<div class="actions">
		<button>Confim</button>
	</div>
</fieldset>
<style>
	fieldset {
		max-width: 20rem;
	}
	.inputs, .actions {
		padding: 0.5rem 1rem;
		text-align: right;
	}

</style>
