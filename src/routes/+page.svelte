<script>
    const { data } = $props()
    let user = $state(data.user)
</script>
<h1>Üdvözöljük a céges eszköz-nyilvántartó programunkban!</h1>
{#if user}
    <h3>Jelenleg bejelentkezve: {user.name}</h3>
{:else}
    <a href="/demo/lucia">Bejelentkezés</a>
{/if}