<template>
    <div class="calculator">
        <label for="numero1">Número 1:</label>
        <input v-model="numero1" type="number" id="numero1" @input="calcularResultado">

        <label for="operacao">Operação:</label>
        <select v-model="operacao" id="operacao" @change="calcularResultado">
            <option value="+">+</option>
            <option value="-">-</option>
            <option value="*">*</option>
            <option value="/">/</option>
        </select>

        <label for="numero2">Número 2:</label>
        <input v-model="numero2" type="number" id="numero2" @input="calcularResultado">

        <p class="resultado">Resultado: {{ resultado }}</p>
    </div>
</template>
  
<script>
export default {
    data() {
        return {
            numero1: 0,
            operacao: '+',
            numero2: 0,
            resultado: 0
        };
    },
    methods: {
        calcularResultado() {
            switch (this.operacao) {
                case '+':
                    this.resultado = this.numero1 + this.numero2;
                    break;
                case '-':
                    this.resultado = this.numero1 - this.numero2;
                    break;
                case '*':
                    this.resultado = this.numero1 * this.numero2;
                    break;
                case '/':
                    this.resultado = this.numero1 / this.numero2;
                    break;
                default:
                    this.resultado = 0;
            }
        }
    }
};
</script>
  
<style scoped>
.calculator {
    max-width: 300px;
    margin: 20px auto;
    padding: 20px;
    border: 1px solid #ccc;
    border-radius: 5px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

label {
    display: block;
    margin-bottom: 5px;
}

input,
select {
    width: 100%;
    padding: 8px;
    margin-bottom: 15px;
    box-sizing: border-box;
}

p.resultado {
    font-weight: bold;
}
</style>
  