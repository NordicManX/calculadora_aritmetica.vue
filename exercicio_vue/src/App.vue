<script>

export default {
 data() {
    return {
      number1: '',
      number2: '',
      selectedOperation: '',
      operations: [
        { name: 'Soma', value: '+' },
        { name: 'Subtração', value: '-' },
        { name: 'Multiplicação', value: '*' },
        { name: 'Divisão', value: '/' },
      ],
      result: '',
    };
 },
 methods: {
    calculate() {
      switch (this.selectedOperation) {
        case '+':
          this.result = parseFloat(this.number1) + parseFloat(this.number2);
          break;
        case '-':
          this.result = parseFloat(this.number1) - parseFloat(this.number2);
          break;
        case '*':
          this.result = parseFloat(this.number1) * parseFloat(this.number2);
          break;
        case '/':
          this.result = parseFloat(this.number1) / parseFloat(this.number2);
          break;
        default:
          this.result = '';
      }
    },
 },
};

</script>

<template>

  
 <div class="container">
  <h1>Calculadora Aritmética!</h1>
    <div class="row">
        <div class="col-md-4">
            <input type="number" class="form-control" v-model="number1" @input="calculate()">
        </div>
        <div class="col-md-4">
            <select class="form-control" v-model="selectedOperation" @change="calculate()">
                <option v-for="operation in operations" :key="operation.value" :value="operation.value">
                    {{ operation.name }}
                </option>
            </select>
        </div>
        <div class="col-md-4">
            <input type="number" class="form-control" v-model="number2" @input="calculate()">
        </div>
    </div>
    <div class="row mt-3">
        <div class="col-md-12">
            <h3>Resultado: {{ result }}</h3>
            
        </div>
    </div>
 </div>
</template>

<style scoped>


.container h1 {
  text-align: center;
  font-size: 24px;
  margin-top: 50px;
  
}

.form-control {
  margin-top: 50px;
margin-bottom: 50px;
}

.row {
  text-align: center;
}
</style>
