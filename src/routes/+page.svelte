<script>
    const { data } = $props()
    let user = $state(data.user)
</script>
<h1>Céges eszköz-nyilvántartó program</h1>
{#if user}
    <h3>Bejelentkezve: {user.name}</h3>
{:else}
    <a href="/demo/lucia">Bejelentkezés</a>
{/if}