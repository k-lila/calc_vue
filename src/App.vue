<template>
  <div class="container">
    <div class="calculadora">
      <div class="calculadora__title">
        <h1>Calculadora Aritmética</h1>
      </div>
      <div class="calculadora__calc inputs">
        <div class="inputs__num">
          <input type="number" v-model="num1" @change="atualizaNum">
        </div>
        <div class="inputs__select">
          <select v-model="operator" @click="atualizaNum">
            <option value="+">+</option>
            <option value="-">-</option>
            <option value="x">x</option>
            <option value="/">/</option>
          </select>
        </div>
        <div class="inputs__num">
          <input type="number" v-model="num2" @change="atualizaNum">
        </div>
      </div>
      <div class="calculadora__result">
        <span>{{ resultado }}</span>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        operator: '+',
        num1: 0,
        num2: 0,
        resultado: 0,
      }
    },
    methods: {
      atualizaNum() {
        const n1 = this.num1;
        const n2 = this.num2;
        if (this.operator == '+') {
          this.resultado = n1 + n2;        
        } else if (this.operator == '-') {
          this.resultado = n1 - n2;
        } else if (this.operator == 'x') {
          this.resultado = n1 * n2
        } else if (this.operator == '/') {
          this.resultado = n1 / n2
        }
      }
    }
  }
</script>



<style lang="less" scoped>
  *{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  .container {
    height: 90vh;
    position: relative;
  }

  .calculadora {
    position: absolute;
    top: 20%;
    left: 50%;
    transform: translate(-50%, 50%);
    width: max-content;
    border: 3px solid black;
    border-radius: 10px;
    &__title,
    &__calc,
    &__result,
    &__operators {
      display: flex;
      justify-content: center;
    }
    &__title {
      font-size: 150%;
      text-align: center;
      padding: 15px;
    }
    &__result {
      font-size: 200%;
      padding: 3%;
    }
  }

  .inputs {
    background-color: black;

  }

</style>
