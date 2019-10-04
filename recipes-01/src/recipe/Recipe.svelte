<script>
  export let title;
  export let ingredients;

  function removeIngredient(toRemove) {
    ingredients = ingredients.filter(
      ingredient => ingredient.description !== toRemove.description
    );
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
