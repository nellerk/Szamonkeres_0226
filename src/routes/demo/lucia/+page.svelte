<script>
	import { enhance } from '$app/forms';

	let { data } = $props();
</script>

<h1>Bejelentkezve: {data.user.name}</h1>
<form method="post" action="?/logout" use:enhance>
	<button class="ui red button">Kijelentkezés</button>
</form>
