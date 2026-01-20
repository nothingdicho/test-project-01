<template>
  <div class="calculator">
    <input type="number" v-model="number1" placeholder="Number 1" />
    <input type="number" v-model="number2" placeholder="Number 2" />
    <div class="buttons">
      <button @click="add">+</button>
      <button @click="subtract">-</button>
      <button @click="multiply">*</button>
      <button @click="divide">/</button>
      <button @click="clear">C</button>
    </div>
    <div class="result">Result: {{ result }}</div>
  </div>
</template>
