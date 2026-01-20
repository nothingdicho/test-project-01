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
 <script>
export default {
  data() {
    return {
      number1: 0,
      number2: 0,
      result: 0
    };
  },
  methods: {
    add() {
      this.result = this.number1 + this.number2;
    },
    subtract() {
      this.result = this.number1 - this.number2;
    },
    multiply() {
      this.result = this.number1 * this.number2;
    },
    divide() {
      if (this.number2 !== 0) {
        this.result = this.number1 / this.number2;
      } else {
        this.result = Error;
      }
    },
    clear() {
      this.number1 = 0;
      this.number2 = 0;
      this.result = 0;
    }
  }
};
</script>
