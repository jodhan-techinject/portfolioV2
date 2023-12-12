<script>
	import Social from '../atoms/Social.svelte';
	import { user } from '../../util/discord';
</script>

<div class="socials-container">
	<Social icon="github" tip="Jodhansajifab" link="https://github.com/Jodhansajifab" />
	<Social icon="discord" tip={user.username} link={`https://discord.com/users/${user.id}`} />
	<Social icon="email" tip="jodhan.saji@gmail.com" link="mailto:jodhan.saji@gmail.com" />
	<Social icon="kofi" tip="affan" link="https://ko-fi.com/affan" />
</div>

<style>
	.socials-container {
		display: flex;
		gap: 0.75rem;
	}
</style>
