<script>
	import CardForm from './cardForm.svelte';
	import CardBack from './cardBack.svelte';
	import CardFront from './cardFront.svelte';
	let cardDetails = {};
	function handleCardDetails(event) {
		cardDetails = event.detail;
	}
</script>

<div class="main">
	<CardBack {cardDetails} />
	<CardFront {cardDetails} />
	<div class="blurred-background" />
	<div class="card-form">
		<CardForm {cardDetails} on:cardDetails={handleCardDetails} />
	</div>
</div>

<style>
	.card-form {
		display: grid;
		place-items: center;
	}

	* {
		margin: 0;
		padding: 0;
	}

	.main {
		display: grid;
		grid-template-columns: 2fr 5fr;
		position: relative;
		width: 100%;
		height: 100vh;
	}

	@media screen and (max-width: 999px) {
		.main {
			grid-template-columns: 1fr;
			grid-template-rows: 3fr 5fr;
		}
	}

	.blurred-background {
		background-image: url(./assets/bg-main-desktop.png);
		background-size: cover;
	}
</style>
