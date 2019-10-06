<script>
  import Product from "./Product.svelte";
  import Hint from "../ui/Hint.svelte";
  export let products;
</script>

<style>
  ul {
    margin: 0;
    padding: 0;
    list-style: none;
  }
</style>

{#if products && products.length > 0}
  <ul>
    {#each products as product}
      <li>
        <Product title={product} />
      </li>
    {/each}
  </ul>
{:else}
  <Hint icon="pepper-hot">Ziemlich leer hier</Hint>
{/if}
