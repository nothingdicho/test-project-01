<script lang='ts'>
let num1: number = 0;
let num2: number = 0;
let result: number = 0;
function add() { result = num1 + num2; }
function subtract() { result = num1 - num2; }
function multiply() { result = num1 * num2; }
function divide() { result = num2 !== 0 ? num1 / num2 : 0; }
</script>
<main>
  <h1>Simple Calculator</h1>
  <input type='number' bind:value={num1} placeholder='Number 1' />
  <input type='number' bind:value={num2} placeholder='Number 2' />
  <button on:click={add}>+</button>
  <button on:click={subtract}>-</button>
  <button on:click={multiply}>*</button>
  <button on:click={divide}>/</button>
  <h2>Result: {result}</h2>
</main>
