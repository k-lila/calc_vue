<template>
    <div class="calculadora">
        <div class="calculadora__title">
            <h1>Calculadora Aritmética</h1>
        </div>
        <div class="calculadora__calc inputs">
            <input type="number" v-model="num1" @change="atualizaNum">
            <div>
                <select v-model="operator" @click="atualizaNum">
                    <option value="+">+</option>
                    <option value="-">-</option>
                    <option value="x">x</option>
                    <option value="/">/</option>
                </select>
            </div>
            <input type="number" v-model="num2" @change="atualizaNum">
        </div>
        <div class="calculadora__result">
            <span>{{ resultado }}</span>
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
    .calculadora {
        position: absolute;
        align-items: center;
        left: 50%;
        transform: translate(-50%, 50%);
        width: 100%;
        max-width: 450px;
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
            padding: 10px 15px 0 15px;
        }

        &__result {
            font-size: 200%;
            padding: 3%;
        }
    }

    .inputs {
        justify-content: space-between;
        max-width: 350px;
        margin: 0 auto;
        padding: 1%;
        input,
        select {
            font-size: 125%;
            padding: 2px;
            border: 2px solid black;
            border-radius: 3px;
            background-color: transparent;
        }
        input {
            width: 100%;
            max-width: 100px;
        }
        select {
            margin: 0 10px;
        }
    }
</style>