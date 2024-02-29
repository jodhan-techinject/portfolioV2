<script>
	import WebGrid from '../molecules/WebGrid.svelte';
	import Tooltip from '../atoms/Tooltip.svelte';
</script>

<section>
	<div class="wrapper" id="aw">
		<Tooltip tip="Click on an website">
			<h2><span>Builds</span> : and Collaborations</h2>
		</Tooltip>
	</div>
	<WebGrid />
</section>

<style lang="scss">
	span {
		color: var(--orange);
	}

	h2 {
		display: inline-block;
		margin-bottom: 1rem;
	}

	div {
		display: flex;
		justify-content: center;
		margin-top: 0;

		@media (max-width: 868px) {
			justify-content: left;
			margin-bottom: 0.3rem;
		}
	}
</style>
