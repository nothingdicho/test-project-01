<script>
  let currentInput = '';
  let result = '';

  function appendNumber(number) {
    currentInput += number;
  }

  function setOperation(operation) {
    if (currentInput) {
      result = eval(currentInput);
      currentInput = '';
    }
  }

  function calculate() {
    if (currentInput) {
      result = eval(currentInput);
      currentInput = '';
    }
  }
</script>

<style>
  /* Add your styles here */
</style>

<div>
  <input type=text bind:value={currentInput} readonly />
  <div>
    <button on:click={() => appendNumber('1')}>1</button>
    <button on:click={() => appendNumber('2')}>2</button>
    <button on:click={() => appendNumber('3')}>3</button>
    <button on:click={() => setOperation('+')}>+</button>
  </div>
  <div>
    <button on:click={() => appendNumber('4')}>4</button>
    <button on:click={() => appendNumber('5')}>5</button>
    <button on:click={() => appendNumber('6')}>6</button>
    <button on:click={() => setOperation('-')}>-</button>
  </div>
  <div>
    <button on:click={() => appendNumber('7')}>7</button>
    <button on:click={() => appendNumber('8')}>8</button>
    <button on:click={() => appendNumber('9')}>9</button>
    <button on:click={() => setOperation('*')}>*</button>
  </div>
  <div>
    <button on:click={() => appendNumber('0')}>0</button>
    <button on:click={calculate}>=</button>
    <button on:click={() => setOperation('/')}>F7</button>
  </div>
</div>
