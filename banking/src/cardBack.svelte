<script>
	export let cardDetails;
</script>

<div class="card-back">
	<div class="card-back-inner">
		<div id="onCardCvc">{cardDetails.cvc || '123'}</div>
	</div>
</div>

<style>
	.card-back {
		background-image: url(./assets/bg-card-back.png);
		background-size: cover;
		background-repeat: no-repeat;
		width: 300px;
		height: 160px;
		border-radius: 7px;
		display: grid;
		place-items: center;
		position: absolute;
		color: white;
		top: 50%;
		left: 15%;
	}

	@media screen and (max-width: 999px) {
		.card-back {
			top: 5%;
			right: 1rem;
			z-index: 10;
		}
	}

	.card-back-inner {
		width: calc(100% - 3rem);
		height: calc(100% - 2rem);
		/* border: 1px solid red; */
		position: relative;
	}

	#onCardCvc {
		position: absolute;
		right: 1em;
		top: 45%;
		font-size: 0.8em;
	}
</style>
