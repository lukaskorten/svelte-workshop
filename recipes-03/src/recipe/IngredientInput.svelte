<script>
  import IconButton from "../ui/IconButton.svelte";

  let description;
  let amount;
  let unit;
</script>

<style>
  form {
    margin: 0;
  }

  section {
    background: #ffffff;
    box-shadow: 0 3px 8px -3px rgba(0, 0, 0, 0.15);
    border-radius: 0.5rem;
    padding: 1rem;
    margin: 0 -1rem;
  }

  .content {
    display: flex;
    justify-content: space-between;
  }

  .footer {
    display: flex;
    justify-content: flex-end;
    margin-top: 1rem;
  }

  input,
  select {
    border: 2px solid #f5f5f5;
    outline: none;
    border-radius: 6px;
    background: #f5f5f5;
    padding: 0.5rem 0.75rem;
    color: #616161;
    margin: 0;
  }

  input:focus,
  select:focus {
    background: #fafafa;
  }

  input::placeholder {
    opacity: 0.4;
  }

  .description {
    flex-grow: 1;
  }

  .amount,
  select {
    width: 5rem;
    margin-left: 0.5rem;
  }

  [disabled] {
    opacity: 0.5;
  }
</style>

<form>
  <section>
    <div class="content">
      <input class="description" type="text" placeholder="Was fehlt noch?" />
      <input class="amount" type="number" placeholder="100" />
      <select>
        <option value="" disabled selected>Stück</option>
        <option value="g">g</option>
        <option value="ml">ml</option>
        <option value="TL">TL</option>
      </select>
    </div>
    <div class="footer">
      <IconButton type="reset">Abbrechen</IconButton>
      <IconButton type="submit" mode="primary">Hinzufügen</IconButton>
    </div>
  </section>
</form>
