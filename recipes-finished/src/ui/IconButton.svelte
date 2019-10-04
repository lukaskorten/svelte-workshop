<script>
  export let icon = null;
  export let type = "button";
  export let mode = "default";
  export let title = "";

  $: iconClass = icon ? `fas fa-${icon}` : "hidden";
</script>

<style>
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

  button:last-of-type {
    margin-right: 0;
  }
  button:first-of-type {
    margin-left: 0;
  }

  button:hover {
    color: #00897b;
    background: #fcfcfc;
  }

  button.primary {
    color: #00897b;
    background: #fafafa;
  }

  button.primary:hover {
    color: #00554d;
    background: #fcfcfc;
  }

  button.warning:hover {
    color: #fa9417;
  }

  .hidden {
    display: none;
  }
</style>

<button class={mode} on:click {title} {type}>
  <i class={iconClass} />
  <slot />
</button>
