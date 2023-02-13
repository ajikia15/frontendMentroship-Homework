<script>
	import { createEventDispatcher } from 'svelte';
	export let cardDetails;
	let name = '';
	let num = '';
	let mm = '';
	let yy = '';
	let cvc = '';
	function submit() {
		cardDetails = { name, num, mm, yy, cvc };
		dispatch('cardDetails', cardDetails);
	}
	const dispatch = createEventDispatcher();
</script>

<div class="form">
	<form>
		<label for="cardName">CARDHOLDER NAME</label>
		<input type="text" id="cardName" name="cardName" placeholder="" bind:value={name} />
	</form>

	<form action="">
		<label for="cardNum">CARD NUMBER</label>
		<input type="text" id="cardNum" name="cardNum" maxlength="19" bind:value={num} />
	</form>
	<div class="form-split-titles">
		<label for="">EXPIRING DATE(MM/YY)</label>
		<label for="" style="">CVC</label>
	</div>
	<div class="form-split" style="">
		<div class="" style="">
			<input
				type="text"
				id="mm"
				name="mm"
				maxlength="2"
				size="1"
				style="margin-right:10px"
				bind:value={mm}
			/>
			<input type="text" id="yy" name="yy" maxlength="2" size="1" bind:value={yy} />
		</div>
		<div class="">
			<input
				style="float:right"
				type="text"
				id="cvc"
				name="cvc"
				maxlength="3"
				size="10"
				bind:value={cvc}
			/>
		</div>
	</div>
	<form>
		<input type="button" id="submitBtn" value="Submit" on:click={submit} />
	</form>
</div>

<style>
	.form-split-titles {
		display: flex;
		justify-content: space-between;
	}

	.form-split {
		display: flex;
		justify-content: space-between;
		flex-direction: row;
	}

	.form-split div {
		width: 100%;
	}

	@media screen and (max-width: 999px) {
		.form-split {
			display: flex;
		}

		.form-split div {
			width: 100%;
		}
	}

	.form {
		min-width: 200px;
		width: 40%;
		display: flex;
		flex-direction: column;
	}

	@media screen and (max-width: 999px) {
		.form {
			width: 70%;
		}
	}

	input[type='text'] {
		padding: 8px;
		border: 1px solid #9236e8;
		border-radius: 4px;
	}

	form {
		display: flex;
		flex-direction: column;
	}

	label {
		font-size: 0.6em;
		font-weight: bolder;
		margin-top: 20px;
	}

	#submitBtn {
		margin-top: 20px;
		background-color: #23082f;
		border: 1px solid#fff;
		border-radius: 4px;
		padding: 12px;
		cursor: pointer;
		color: white;
		transition: 0.5s all;
	}

	#submitBtn:hover {
		background-color: white;
		border: 1px solid #23082f;
		color: #23082f;
	}
</style>
