<script lang="ts">
	import { fly } from 'svelte/transition';
	import { cubicOut, quintOut } from 'svelte/easing';

	export let tall = false;
	export let website = '';
	export let websiteTitle = '';
	export let technologies = '';
	export let websiteLink = '';
	export let shrink = false;
	export let subtitle = 'Click on the image to navigate to the website';

	let clicked = false;

	function onKeyDown(e: KeyboardEvent) {
		if (e.key === 'Escape') {
			clicked = false;
		}
	}

</script>

<button
	aria-label={website}
	class="card"
	class:tall
	class:shrink
	on:click={() => (clicked = true)}
	on:keypress={() => (clicked = true)}
	style="background-image:url(websites/{website}.png)"
/>

<svelte:window on:keydown={onKeyDown} />

<svelte:head>
	{#if clicked}
		<title>Jodhan · {website}</title>
	{:else}
		<title>Jodhan</title>
	{/if}
</svelte:head>

{#if clicked === true}
	<!-- svelte-ignore a11y-no-noninteractive-tabindex -->
	<div
		class="img-modal"
		tabindex="0"
		on:click={() => (clicked = false)}
		on:keypress={() => (clicked = false)}
		in:fly={{ y: 50, easing: quintOut, duration: 750 }}
		out:fly={{ y: 50, easing: cubicOut, duration: 300 }}
	>
		<h3>{websiteTitle}</h3>
		<h5 class="py-2">{technologies}</h5>
		<a href="{websiteLink}" target="_blank">
			<img loading="lazy" src="websites/{website}.png" alt={website} />
		</a>
		<h6>{subtitle}</h6>
	</div>
{/if}

<style lang="scss">
  .card {
    position: relative;
    border: none;
    padding: 0;
    height: 100%;
    width: 100%;
    border-radius: 20px;
    overflow: hidden;
    background: var(--neutral-one);
    transition: all 0.3s var(--bezier-one);
    cursor: pointer;
    font-size: 0;
    user-select: none;
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
    -webkit-transform: translate3d(0, 0, 1px);
    -webkit-backface-visibility: hidden;


    &:hover {
      transform: translateY(-1px);
      box-shadow: 0px 15px 25px -10px rgba(0, 0, 0, 0.25);
    }

    @media screen and (max-width: 868px) {
      border-radius: 0;
    }
  }

  .card::before {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: linear-gradient(rgba(0, 0, 0, 0.1), rgba(193, 90, 43, 0.44));
  }

  .img-modal {
    background-blend-mode: overlay;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    position: fixed;
    text-align: center;
    left: 0;
    top: 50%;
    transform: translateY(-50%);
    height: 200vh;
    width: 100vw;
    z-index: 20;
    cursor: pointer;
    user-select: none;
    background-color: #0a0808bb;
    backdrop-filter: blur(12px);
    -webkit-backdrop-filter: blur(12px);

    img {
      max-height: 83vh;
      height: auto;
      max-width: 86vw;
      border-radius: 2vh;
      display: flex;
      justify-content: center;
      align-items: center;
    }
  }

  h3,
  h6 {
    margin: 1vh;
  }

  h6 {
    font-size: 2vh;
    margin-top: 2vh;
  }

  h3 {
    font-size: 3.5vh;
    font-weight: 500;
    color: var(--white);
  }

  .tall {
    grid-row: span 2 / auto;
  }

	.py-2{
		padding-bottom: .5rem;
	}

  @media only screen and (max-width: 1153px) {
    .shrink {
      grid-row: span 1 / auto;
      background-position: top;
    }
  }
</style>
