<script>
  export let items
</script>

{#each items as item (item.id)}
  <article class="list-item">
    <h3>{item.title}</h3>
    <p>{@html item.description}</p>
    {#if item.link.video}
    {/if}
  </article>
{/each}

<style>
  .list-item {
    border-bottom: 1px solid black;
  }

  .list-item:last-child {
    border-bottom: none;
  }
</style>

