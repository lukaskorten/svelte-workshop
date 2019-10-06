<script>
  import { flip } from "svelte/animate";
  import { slide } from "svelte/transition";
  import { createEventDispatcher } from "svelte";
  import Ingredient from "./Ingredient.svelte";
  import Button from "../ui/Button.svelte";
  import IconButton from "../ui/IconButton.svelte";
  import IngredientInput from "./IngredientInput.svelte";

  export let title;
  export let ingredients;

  const dispatch = createEventDispatcher();
  let isInputVisible = false;

  function showInput() {
    isInputVisible = true;
  }

  function hideInput() {
    isInputVisible = false;
  }

  function addIngredient(e) {
    const ingredient = { ...e.detail };
    ingredients = [...ingredients, ingredient];
    hideInput();
  }

  function removeIngredient(e) {
    const ingredientName = e.detail;
    ingredients = ingredients.filter(
      ingredient => ingredient.description !== ingredientName
    );
  }

  function toShoppingList() {
    dispatch("toshoppinglist", { title, ingredients });
  }
</script>

<style>
  .recipe {
    width: 25rem;
    border-radius: 0.5rem;
    padding: 1rem 2rem;
    box-shadow: 0 15px 25px -10px rgba(0, 0, 0, 0.15);
    background: #fefefe;
    margin: 0 0 1rem;
  }

  h2 {
    margin: 1rem 0 2rem 0;
    color: #00695c;
  }

  ul {
    padding: 0;
    list-style: none;
    color: #616161;
    margin: 0 0 2rem;
  }

  li {
    padding: 0;
  }

  .ingredient-input-container {
    margin: 0 0 1rem;
  }

  .ingredients-footer {
    display: flex;
    justify-content: center;
  }

  .footer {
    display: flex;
    justify-content: center;
    padding-top: 1rem;
    margin-top: 1rem;
    box-shadow: 0 -15px 20px -25px rgba(0, 0, 0, 0.25);
  }
</style>

<div class="recipe">
  <h2>{title}</h2>
  <ul>
    {#each ingredients as ingredient (ingredient)}
      <li animate:flip={{ duration: 250 }}>
        <Ingredient {...ingredient} on:remove={removeIngredient} />
      </li>
    {/each}
  </ul>

  {#if isInputVisible}
    <div
      class="ingredient-input-container"
      transition:slide={{ duration: 250 }}>
      <IngredientInput on:save={addIngredient} on:cancel={hideInput} />
    </div>
  {/if}

  <div class="ingredients-footer">
    <IconButton on:click={showInput}>Zutat hinzufügen</IconButton>
  </div>

  <div class="footer">
    <Button on:click={toShoppingList}>Auf die Einkaufsliste</Button>
  </div>
</div>
