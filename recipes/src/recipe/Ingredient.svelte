<script>
  import IconButton from "../ui/IconButton.svelte";
  import { createEventDispatcher } from "svelte";

  export let amount = null;
  export let unit = null;
  export let description;

  const dispatch = createEventDispatcher();

  function remove() {
    dispatch("remove", description);
  }
</script>

<style>
  div {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .ingredient {
    padding: 0.4rem 0;
  }

  .amount {
    color: #b5b2aa;
  }

  .buttons {
    opacity: 0.1;
    transition: opacity ease 250ms;
  }

  div:hover .buttons {
    opacity: 1;
  }
</style>

<div>
  <span class="ingredient">
    <span class="amount">
      {#if amount}{amount}{/if}
      {#if unit}{unit}{/if}
    </span>
    {description}
  </span>
  <span class="buttons">
    <IconButton
      icon="trash"
      mode="warning"
      title="{description} entfernen"
      on:click={remove} />
  </span>
</div>
