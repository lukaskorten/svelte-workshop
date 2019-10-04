<script>
  import { recipes } from "./recipes.js";
  import Recipe from "./recipe/Recipe.svelte";

  let title = "American Pancakes";
  let ingredients = [
    { amount: 50, unit: "g", description: "Butter" },
    { amount: 250, unit: "g", description: "Mehl" },
    { amount: 80, unit: "g", description: "Zucker" },
    { amount: 2, unit: "TL", description: "Backpulver" },
    { amount: 0.5, unit: "TL", description: "Salz" },
    { amount: 300, unit: "ml", description: "Milch" },
    { amount: 1, description: "Ei" },
    { amount: 2, unit: "EL", description: "Öl" }
  ];

  function addToShoppingList(event) {
    const ingredients = event.detail.ingredients;
    const products = ingredients.map(ingredient => ingredient.description);
    const message = `Deine Einkausliste enthält: ${products.join(",")}`;
    alert(message);
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
</style>

<header>
  <div class="container">
    <h1>Recipes</h1>
  </div>
</header>

<main>
  <div class="container">
    <div class="card recipe-details">
      <h3>Rezept prüfen/ ändern</h3>
      <Recipe {title} {ingredients} on:toshoppinglist={addToShoppingList} />
    </div>
  </div>
</main>
