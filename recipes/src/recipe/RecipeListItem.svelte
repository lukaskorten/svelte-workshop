<script>
  export let recipe;
</script>

<style>
  button {
    display: inline-flex;
    align-items: center;
    width: 100%;
    text-align: left;
    background: transparent;
    border: none;
    outline: none;
    border-radius: 0.5rem;
    padding: 0.25rem 0;
    margin: 0 0 0.25rem;
    color: #6c6c6c;
    cursor: pointer;
    transition: color 250ms ease-in;
  }
  button:hover {
    color: #00897b;
  }

  button:hover i {
    color: #00a796;
  }

  i {
    margin: 0 0.5rem 0 0;
    color: #9b9b9b;
  }
</style>

<button on:click>
  <i class="fas fa-chevron-right fa-xs" />
  {recipe.title}
</button>
