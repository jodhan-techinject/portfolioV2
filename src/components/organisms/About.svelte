<script>
	import Terminal from '../molecules/Terminal.svelte';
	import Tooltip from '../atoms/Tooltip.svelte';
	import Globe from '../molecules/Globe.svelte';
	import OrdbitingCirclesGroup from '../molecules/OrdbitingCirclesGroup.svelte';

	let getAge = () => {
		let birthDate = new Date('2000/09/15');
		const ageMs = Date.now() - birthDate.getTime();
		return (ageMs / 31536000000).toFixed(10);
	};

	let age = getAge();
	setInterval(() => {
		age = getAge();
	}, 1000);
</script>

<section id="about" class="wrapper">
	<!--	<div class="terminal">-->
	<!--		<Terminal />-->
	<!--	</div>-->
	<div class="circles">
				<OrdbitingCirclesGroup />
	</div>
	<div class="text">
		<h2>bio</h2>
		<p style="">
			Hey there, I'm Jodhan Saji ! I'm a
			<Tooltip tip={age}
			><span>{Math.floor(Number(age))}</span></Tooltip>
			year old Web Developer based in India. Computer Science and Engineering major from
			<Tooltip tip="Lovely Professional University">
				<a href="https://www.lpu.in/" target="_blank" rel="noreferrer">
					<span>LPU,</span>
				</a>
			</Tooltip>
			currently working in
			<Tooltip tip="Tech Inject">
				<a href="https://www.techinject.in/" target="_blank" rel="noreferrer">
					<span>Tech Inject Global Solutions</span>
				</a>
			</Tooltip>
			as Full Stack Web developer. Proficient in Svelte, React, Node, Firebase, Linux and Typescript.
		</p>
	</div>
</section>

<style lang="scss">
  @import '../../styles/mixins.scss';

  .circles {
    display: block;
  }

  section {
    margin-bottom: 6rem;
    display: grid;
    gap: 4.5rem;
    grid-template-columns: 1fr 1fr;
    align-items: center;
  }

  .text {
    position: relative;
    line-height: 1.75rem;
  }

  span {
    font-weight: 400;
    font-family: var(--font-two);
    font-size: 0.9rem;
    background-color: var(--neutral-one);
    border-radius: 7px;
    color: var(--orange);
    padding: 0.2rem 0.5rem 0.2rem;
    width: fit-content;
  }

  a {
    text-decoration: none;
  }

  .text::before {
    @include outlineText($content: 'JOD', $translateX: 97%, $translateY: -5%, $fontSize: 250px, $opacity: 0.22);
  }

  h2 {
    display: none;
    margin-top: 1rem;
  }

  @media (max-width: 868px) {
    .circles {
      display: none;
    }

    section {
      display: flex;
      flex-direction: column;
      align-items: normal;
    }

    h2 {
      display: block;
      margin-bottom: 1rem;
    }
  }
</style>
