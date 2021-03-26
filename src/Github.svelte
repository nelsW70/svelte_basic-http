<script>
  // modules
  import { onMount } from "svelte";
  // variables
  let users = [];
  let loading = true;
  // lifecycles
  onMount(async () => {
    let userData = await fetch("https://api.github.com/users");
    let githubUsers = await userData.json();
    console.log(githubUsers);
  });
</script>

<style>
  h2 {
    text-align: center;
  }
</style>

{#if loading}
  <h2>Loading...</h2>
{:else}
  <h2>Data</h2>
{/if}
