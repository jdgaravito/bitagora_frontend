<script>
  import { onMount } from "svelte";
  let data = [];
  onMount(async function() {
    const response = await fetch("https://academy.valentinog.com/api/link/");
    const json = await response.json();
    data = json;
  });
</script>

<ul>
  {#each data as link}
    <li>
      <a href={link.url}>{link.title}</a>
    </li>
  {/each}
</ul>
