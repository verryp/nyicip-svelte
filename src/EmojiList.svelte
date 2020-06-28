<script>
  export let emojis;
</script>

<style>
  ul {
    text-align: center;
  }

  li {
    display: inline-block;
  }
</style>

<div>
  <ul>
    {#each emojis as emoji}
      <li>{emoji}</li>
    {/each}
  </ul>
</div>
