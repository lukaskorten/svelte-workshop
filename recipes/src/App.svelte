<script>
  import { recipes } from "./recipes.js";
  import RecipeListItem from "./recipe/RecipeListItem.svelte";
  import Recipe from "./recipe/Recipe.svelte";
  import ShoppingList from "./shoppinglist/ShoppingList.svelte";
  import Hint from "./ui/Hint.svelte";

  let selectedRecipe;
  let shoppingList = [];

  function selectRecipe(recipe) {
    selectedRecipe = recipe;
  }
  function addToShoppingList(e) {
    const ingredients = e.detail.ingredients;
    const products = ingredients.map(ingredient => ingredient.description);
    shoppingList = [...shoppingList, ...products].filter(
      (value, index, self) => {
        return self.indexOf(value) === index;
      }
    );
  }
</script>

<style>
  header {
    height: 6rem;
    display: flex;
    justify-content: center;
    align-items: center;
    background: #f9f9f9;
    border-bottom: 3px solid #fefefe;
    color: #00695c;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.05);
  }

  main {
    margin-top: 2rem;
  }

  .container {
    width: 85rem;
    margin: 0 auto;
    display: flex;
    justify-content: space-between;
  }

  .card {
    background: rgba(255, 255, 255, 0.4);
    padding: 1rem 2rem;
    border-radius: 0.5rem;
  }

  .recipe-list {
    width: 20rem;
  }
  .recipe-details {
    width: 29rem;
  }
  .shopping-list {
    width: 20rem;
  }

  h2 {
    margin: 2rem 0;
    font-size: 1.2rem;
  }

  ul {
    list-style: none;
    padding: 0;
    margin: 0;
  }
</style>

<header>
  <div class="container">
    <h1>Recipes</h1>
  </div>

</header>

<main>
  <div class="container">
    <div class="card recipe-list">
      <h2>
        <i class="fas fa-cookie-bite" />
        Rezept auswählen...
      </h2>
      <ul>
        {#each recipes as recipe}
          <li>
            <RecipeListItem {recipe} on:click={() => selectRecipe(recipe)} />
          </li>
        {/each}
      </ul>
    </div>
    <div class="card recipe-details">
      <h2>
        <i class="fas fa-search" />
        Zutaten prüfen/ ändern ...
      </h2>
      {#if selectedRecipe}
        <Recipe {...selectedRecipe} on:toshoppinglist={addToShoppingList} />
      {:else}
        <Hint icon="file-alt">Such dir ein Rezept aus</Hint>
      {/if}
    </div>
    <div class="card shopping-list">
      <h2>
        <i class="fas fa-shopping-cart" />
        Einkaufsliste
      </h2>
      <ShoppingList products={shoppingList} />
    </div>
  </div>
</main>
