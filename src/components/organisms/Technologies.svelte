<script lang="ts">
	import technologies from '../../util/technologies.json'
</script>

<section class="wrapper">
	<div class="title">
		<h2>Tech Stack</h2>
	</div>

	<div class="tech-stack">
		{#each technologies as { name, icon }}
			<div class="tech">
				<img src={icon} alt={name} />
				<h6>{name}</h6>
			</div>
		{/each}
	</div>
</section>

<style lang="scss">
	.title {
		display: flex;
		flex-direction: column;
		align-items: center;
		margin-top: 5rem;
		margin-bottom: 1.5rem;

		@media (max-width: 868px) {
			align-items: normal;
		}
	}

	.tech {
		display: flex;
		flex-direction: column;
		align-items: center;
		gap: 0.5rem;
	}

	.tech-stack {
		justify-content: center;
		display: flex;
		flex-wrap: wrap;
		gap: 2rem;
		margin-bottom: 6rem;
	}

	img {
		border-radius: 50%;
		height: 64px;
		width: 64px;
	}
</style>
