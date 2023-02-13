<script>
	export let cardDetails;
</script>

<div class="card-front">
	<div class="card-front-inner">
		<div class="card-logo">O</div>
		<div class="card-details">
			<div class="card-details-number">
				<p>{cardDetails.num || '0000 0000 0000 0000'}</p>
			</div>
			<div class="card-details-name-expiry">
				<div class="card-details-name">
					<div class="name">
						<p id="onCardName">{cardDetails.name || 'Aleksandre Jikia'}</p>
					</div>
				</div>
				<div class="card-details-expiry">
					<p id="onCardExpiry">
						{cardDetails.mm || '--'}/{cardDetails.yy || '--'}
					</p>
				</div>
			</div>
		</div>
	</div>
</div>

<style>
	.card-front {
		background-image: url(./assets/bg-card-front.png);
		background-size: cover;
		background-repeat: no-repeat;
		width: 300px;
		height: 180px;
		border-radius: 7px;
		display: grid;
		place-items: center;
		position: absolute;
		color: white;
		top: 20%;
		left: 10%;
	}

	@media screen and (max-width: 999px) {
		.card-front {
			top: 20%;
			left: 1rem;
			z-index: 10;
		}
	}

	.card-front-inner {
		display: grid;
		grid-template-columns: 1fr;
		grid-template-rows: 1fr;
		width: calc(100% - 3rem);
		height: calc(100% - 2rem);
		/* border: 1px solid red; */
	}

	.card-details-number p {
		font-size: 1.5em;
	}

	.card-details-name-expiry {
		display: flex;
		justify-content: space-between;
		padding-top: 1em;
		align-items: center;
		font-size: 0.75em;
		color: rgb(230, 228, 228);
	}
</style>
