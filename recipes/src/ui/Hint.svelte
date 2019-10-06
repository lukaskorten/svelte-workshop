<script>
  export let icon;
</script>

<style>
  .hint {
    display: flex;
    justify-content: flex-start;
    align-items: center;
    color: #c4c4c4;
  }
  i {
    color: #d7d7d7;
    margin-right: 1rem;
  }
</style>

<div class="hint">
  <i class="fas fa-{icon} fa-3x" />
  <p>
    <slot />
  </p>
</div>
