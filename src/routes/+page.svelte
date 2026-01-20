<script>
  let currentInput = '';
  let result = 0;

  function appendToInput(value) {
    currentInput += value;
  }

  function calculate() {
    result = eval(currentInput);
    currentInput = '';
  }

  function clearInput() {
    currentInput = '';
    result = 0;
  }
</script>

<main>
  <h1>Simple Calculator</h1>
  <div>
    <input type="text" bind:value={currentInput} readonly />
    <div>
      <button on:click={() => appendToInput('1')}>1</button>
      <button on:click={() => appendToInput('2')}>2</button>
      <button on:click={() => appendToInput('3')}>3</button>
      <button on:click={() => appendToInput('+')}>+</button>
      <button on:click={() => calculate()}>=</button>
      <button on:click={() => clearInput()}>C</button>
    </div>
  </div>
</main>

<h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://svelte.dev/docs/kit">svelte.dev/docs/kit</a> to read the documentation</p>

