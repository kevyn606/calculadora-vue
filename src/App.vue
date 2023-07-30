<template>
  <div class="container">
    <h1 class="heading">Calculadora</h1>
    <div class="calculator">
      <input v-model="number1" type="number" class="input" @input="calculate" />
      <select v-model="operation" class="input" @change="calculate">
        <option value="somar">+</option>
        <option value="subtrair">-</option>
        <option value="multiplicar">*</option>
        <option value="dividir">/</option>
      </select>
      <input v-model="number2" type="number" class="input" @input="calculate" />
      <span class="result">= {{ result }}</span>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      number1: 0,
      number2: 0,
      operation: 'add',
      result: 0,
    };
  },
  methods: {
    calculate() {
      switch (this.operation) {
        case 'somar':
          this.result = parseFloat(this.number1) + parseFloat(this.number2);
          break;
        case 'subtrair':
          this.result = parseFloat(this.number1) - parseFloat(this.number2);
          break;
        case 'multiplicar':
          this.result = parseFloat(this.number1) * parseFloat(this.number2);
          break;
        case 'dividir':
          this.result = parseFloat(this.number1) / parseFloat(this.number2);
          break;
      }
    },
  },
};
</script>

<style>
.container {
  background-color: rgb(16, 125, 139);
  width: 50vw;
  border-radius: 4px;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 50px;
}

.heading {
  font-size: 24px;
  font-weight: bold;
}

.calculator {
  display: flex;
  align-items: center;
}

.input {
  margin: 10px;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 4px;
}

.result {
  margin-left: 10px;
  font-weight: bold;
}
</style>
