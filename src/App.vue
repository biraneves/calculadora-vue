<script setup>
import { reactive } from 'vue';
import Header from './components/Header.vue';
import Corpo from './components/Corpo.vue';

const estado = reactive({
    resultado: 0,
    valor1: 0,
    valor2: 0,
    operacao: 'soma',
});

const efetuaCalculo = () => {
    switch (estado.operacao) {
        case 'soma':
            estado.resultado = estado.valor1 + estado.valor2;
            break;
        case 'subtracao':
            estado.resultado = estado.valor1 - estado.valor2;
            break;
        case 'multiplicacao':
            estado.resultado = estado.valor1 * estado.valor2;
            break;
        case 'divisao':
            if (estado.valor2 === 0) {
                estado.resultado = 'E';
            } else {
                estado.resultado = estado.valor1 / estado.valor2;
            }
    }
};

const resetFields = () => {
    estado.resultado = 0;
    estado.valor1 = 0;
    estado.valor2 = 0;
    estado.operacao = 'soma';
};
</script>

<template>
    <div class="container d-flex justify-content-center align-items-center">
        <div class="corpo-calculadora p-3 mt-2 rounded-3">
            <Header />
            <Corpo
                :resultado="estado.resultado"
                :setValor1="e => (estado.valor1 = parseInt(e.target.value))"
                :setValor2="e => (estado.valor2 = parseInt(e.target.value))"
                :setOperacao="e => (estado.operacao = e.target.value)"
                :setResultado="efetuaCalculo"
                :resetFields="resetFields"
            />
        </div>
    </div>
</template>

<style>
#app {
    min-height: 100vh;
}
</style>

<style scoped>
.corpo-calculadora {
    background-color: rgb(27, 27, 27);
}

@media screen and (min-width: 768px) {
    .container {
        min-height: 100vh;
    }
}
</style>
