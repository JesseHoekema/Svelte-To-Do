<script>
  let items = ['Leer Svelte', 'Bouw een app', 'Veel plezier!'];
  let newItem = '';

  function addItem() {
    if (newItem.trim()) {
      items = [...items, newItem];
      newItem = '';
    }
  }
</script>

<main>
  <h1>Todo App</h1>

  <ul>
    {#each items as item}
      <li>{item}</li>
    {/each}
  </ul>
  <h1>Domme idioot</h1>

  <input
    type="text"
    bind:value={newItem}
    placeholder="Voeg een nieuw item toe"
  />
  <button on:click={addItem}>Toevoegen</button>
</main>

<style>
  main {
    font-family: Arial, sans-serif;
    max-width: 600px;
    margin: 0 auto;
    padding: 20px;
    text-align: center;
  }

  ul {
    list-style-type: none;
    padding: 0;
  }

  li {
    margin: 10px 0;
  }

  input {
    padding: 10px;
    font-size: 16px;
  }

  button {
    padding: 10px 15px;
    font-size: 16px;
    margin-left: 10px;
  }
</style>
