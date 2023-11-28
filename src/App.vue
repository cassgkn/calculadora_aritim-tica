<script>
export default {
  data() {
    return {
      num1: '',
      num2: '',
      operation: 'add',
      result: '',
    };
  },
  methods: {
    calculateResult() {
      switch (this.operation) {
        case 'add':
          this.result = this.num1 + this.num2;
          break;
        case 'subtract':
          this.result = this.num1 - this.num2;
          break;
        case 'multiply':
          this.result = this.num1 * this.num2;
          break;
        case 'divide':
          this.result = this.num1 / this.num2;
          break;
        default:
          this.result = 0;
      }
    },
  },
};
</script>

<template>
  <div class="container bg-black text-white pb-5 pt-3">
    <h1 class="text-center">Calculadora Vue</h1>

    <form class="row flex-column justify-content-start align-items-center">
      <h5 class="text-center mb-3 mt-4">Digite abaixo valores para iniciar o cálculo:</h5>
      <div class="col-md-6">
        <div class="form-group mb-3">
          <input class="form-control text-center fw-bold fs-5" v-model="num1" @input="calculateResult" type="number" id="num1" placeholder="Insira o primeiro valor">
        </div>
      </div>
      <div class="col-md-6">
        <div class="form-group mb-3">
          <input class="form-control text-center fw-bold fs-5" v-model="num2" @input="calculateResult" type="number" id="num2" placeholder="Insira o segundo valor">
        </div>
      </div>

      <div class="col-md-6">
        <div class="form-group text-center mb-3">
          <label class="mb-2" for="operation">Selecione o tipo da operação:</label>
          <select class="form-select text-center" v-model="operation" @change="calculateResult" id="operation">
            <option class="fw-bold" value="add">[ + ] Soma</option>
            <option class="fw-bold" value="subtract">[ - ] Subtração</option>
            <option class="fw-bold" value="multiply">[ * ] Multiplicação</option>
            <option class="fw-bold" value="divide">[ / ] Divisão</option>
          </select>
        </div>
      </div>
      <div class="col-6 text-center">
        <h3>Resultado: {{ result }}</h3>
      </div>
    </form>
  </div>
</template>


<style scoped>
 h1 {
  text-align: center;
  margin-top: 30px;
 }

 h3 {
  margin-top: 10px;
  border: none
 }
</style>

