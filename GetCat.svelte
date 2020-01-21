<script>
  import { onMount } from "svelte";

    export const apiURL = "https://northwind.now.sh/api/categories";
    let data = [];
onMount(async function() {
        const response = await fetch(apiURL);
        data = await response.json();
    });
  

</script>

<!-- <style>
  main {
    font-family: sans-serif;
    text-align: center;
  }
</style> -->

<main>
	<ul>
  {#each data as item }
            <li> {item.name}</li>
        {/each}
  </ul>
</main>