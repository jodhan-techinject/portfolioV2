<script>
	import Website from '../atoms/Website.svelte';
</script>

<div class="grid-container">
	<div class="grid">
		<Website tall technologies="React Native, Node.js, Express.js, postgresql" website="pill-up"
						 websiteLink="https://www.pillup.com/"
						 websiteTitle="Pill Up" />
		<Website technologies="Svelte Kit, BootStrap, Firebase" website="not-so-white" websiteLink="https://notsowhite.in/"
						 websiteTitle="Not So White" />
		<Website tall website="lovely-marbles"
						 websiteLink="https://www.lovelymarblessanitations.com/" websiteTitle="Lovely Marbles And Sanitation" />
		<Website website="811" />
		<Website tall website="diverge" />
		<Website tall website="FADE" />
		<Website
			commission
			shrink
			subtitle="Commissioned by Kevin T. · Do not use"
			tall
			website="flandre"
		/>
		<Website tall website="ribbons" />
		<Website website="asumi" />
		<Website website="doodle" />
	</div>
</div>

<style lang="scss">
  @import '../../styles/mixins.scss';

  .grid {
    gap: 0.8rem;
    grid-auto-rows: 230px;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
    width: min(90%, 72rem);

    @media screen and (max-width: 600px) {
      grid-auto-rows: 125px;
    }

    @media screen and (max-width: 868px) {
      width: min(100%, 75rem);
      gap: 0.2rem;
      grid-template-columns: 1fr 1fr 1fr;
    }

    &:before {
      @include outlineText($content: '&&', $translateX: -40%, $translateY: -160%);

      @media screen and (max-width: 868px) {
        @include outlineText($content: '&&', $translateX: -25%, $translateY: -95%);
      }
    }
  }

  .grid-container {
    display: flex;
    justify-content: center;
    margin-bottom: 4rem;
  }
</style>
