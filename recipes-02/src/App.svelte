<script>
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

  function removeIngredient(ingredient) {
    ingredients = ingredients.filter(
      current => current.description !== ingredient.description
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

  .ingredient-container {
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

  .ingredient-container:hover .buttons {
    opacity: 1;
  }

  button {
    background: transparent;
    border: none;
    border-radius: 6px;
    padding: 0.75rem 1rem;
    transition: all 250ms ease-in-out;
    color: #afafaf;
    cursor: pointer;
    margin: 0 0.25rem;
  }

  button:hover {
    color: #fa9417;
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
      <div class="recipe">
        <h2>{title}</h2>
        <ul>
          {#each ingredients as ingredient (ingredient)}
            <li>
              <div class="ingredient-container">
                <span class="ingredient">
                  <span class="amount">
                    {#if ingredient.amount}{ingredient.amount}{/if}
                    {#if ingredient.unit}{ingredient.unit}{/if}
                  </span>
                  {ingredient.description}
                </span>
                <span class="buttons">
                  <button
                    class="warning"
                    on:click={() => removeIngredient(ingredient)}>
                    <i class="fas fa-trash" />
                  </button>
                </span>
              </div>
            </li>
          {/each}
        </ul>
      </div>
    </div>
  </div>
</main>
