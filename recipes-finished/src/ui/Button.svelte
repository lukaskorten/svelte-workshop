<style>
  button {
    background: #00897b;
    border-color: #00897b;
    color: #fefefe;
    padding: 0.75rem 1.5rem;
    border-radius: 4px;
    transition: background-color 250ms ease-in-out;
    cursor: pointer;
  }
  button:hover {
    background: #00a493;
    border-color: #00a493;
  }
  button:active {
    background: #007468;
    border-color: #007468;
  }
</style>

<button on:click>
  <slot />
</button>
