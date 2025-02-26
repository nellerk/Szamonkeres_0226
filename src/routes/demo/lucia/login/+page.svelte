<script >
	import { enhance } from '$app/forms';
	let { form } = $props();
	let login = $state(true);
</script>
{#if login}
	<button onclick={() => login = false}
	class="ui button custom-btn">Regisztráció</button>
	<h1>Bejelentkezés</h1>
{:else}
	<button onclick={() => login = true} 
	class="ui button custom-btn">Bejelentkezés</button>
	<h1>Regisztrációs űrlap</h1>
{/if}
<form class="custom-form" method='post' action='?/login' use:enhance>
	<div class="ui input">
		<div class="ui label custom-lb">Felhasználónév</div>
		<input name='username' />
	</div>
	<div class="ui divider"></div>
	{#if !login}
		<div class="ui input">
			<div class="ui label custom-lb">Név</div>
			<input type='text' name='name' />
		</div>
		<div class="ui divider"></div>
	{/if}
	<div class="ui input">
		<div class="ui label custom-lb">Jelszó</div>
		<input type='password' name='password' />
	</div>
	<div class="ui divider"></div>
	<div>
		{#if login}
			<button class="ui button custom-btn">Bejelentkezés</button>
		{:else}
			<button class="ui button custom-btn" formaction='?/register'>Regisztráció</button>
		{/if}
	</div>
</form>
<p style='color: red'>{form?.message ?? ''}</p>
<style>
	form {
		border: solid 4px #4C0013;
		border-radius: 10px;
		padding: 20px;
		display: inline-flex;
		flex-direction: column;
		background-color: rgb(210, 227, 231);
	}

	.custom-btn {
		background-color: #4C0013;
		color: white;
	}
	
	.custom-form {
		background-color: #B87333;
	}

	.custom-lb {
		background-color: #4C0013;
		color: white;
	}
	
</style>