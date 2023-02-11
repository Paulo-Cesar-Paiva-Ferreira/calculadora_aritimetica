<script >
export default {
  data() {
    return {
      input1: '',
      input2: '',
      operacao: '+'
    };
  },
  computed: {
    resultado() {
      switch (this.operacao) {
        case '+':
          return this.input1 + this.input2;
        case '-':
          return this.input1 - this.input2;
        case '*':
          return this.input1 * this.input2;
        case '/':
          return this.input2 === 0 ? `não é possivel dividir ${this.input1} por 0` : this.input1 / this.input2;
      }
    }
  }
};
</script>

<template>
  <div class="container">
    <h1>Calculadora Aritimética</h1>
    <br>
    <hr>
    <div class="inputs">
      <input v-model.number="input1">
    <select v-model="operacao">
      <option value="+">+</option>
      <option value="-">-</option>
      <option value="*">*</option>
      <option value="/">/</option>
    </select>
    <input v-model.number="input2">
    </div>
    <p>Resultado: <span>{{ resultado }}</span></p>
  </div>
</template>

<style scoped>

.inputs {
  display: flex;
  justify-content: center;
}

*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.container {
  max-width: 550px;
  margin: 0 auto;
  background-color: rgb(234, 241, 241);
  margin-top: 100px;
  display: block;
  align-items: center;
  justify-content: space-between;
  border: solid rgb(190, 182, 182);
  padding: 40px;
  border-radius: 24px 88px 24px 88px;
}

  input {
    width: 80px;
    padding: 8px;
    margin: 16px;
    border-radius: 6px;
    text-align: center;
    font-size: 20px;
    font-weight: bold;
    
  }

  h1{
    text-align: center;
    font-size: 48px;
  }

  p {
    text-align: center;
    font-size: 38px;
  }

  select {
    padding: 8px;
    margin: 16px;
    border-radius: 8px;
    font-size: 20px;
    font-weight: bold;
  }

  span {
    font-weight: bold;
    color: red;
  }
  
</style>
