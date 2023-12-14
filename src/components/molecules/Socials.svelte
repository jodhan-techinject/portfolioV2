<script>
	import Social from '../atoms/Social.svelte';
</script>

<div class="socials-container">
	<Social icon="github" tip="Jodhansajifab" link="https://github.com/Jodhansajifab" />
	<Social icon="linkedin" tip="jodhansaji" link="https://www.linkedin.com/in/jodhansaji/" />
	<Social icon="email" tip="jodhan.saji@gmail.com" link="mailto:jodhan.saji@gmail.com" />
	<Social icon="kofi" tip="affan" link="https://ko-fi.com/affan" />
</div>

<style>
	.socials-container {
		display: flex;
		gap: 0.75rem;
	}
</style>
