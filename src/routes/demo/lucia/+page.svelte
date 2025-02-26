<script>
	import { enhance } from '$app/forms';

	let { data } = $props();
</script>

<h1>Bejelentkezve: {data.user.name}</h1>
<form method="post" action="?/logout" use:enhance>
	<button class="ui button custom-btn">Kijelentkezés</button>
</form>

<style>
	.custom-btn {
		background-color: #4C0013;
		color: white;
	}
</style>