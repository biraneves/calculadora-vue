<script setup>
import Display from './Display.vue';
import Form from './Form.vue';

const props = defineProps([
    'resultado',
    'setValor1',
    'setOperacao',
    'setValor2',
    'clickResultado',
    'setResultado',
    'resetFields',
]);
</script>

<template>
    <main class="w-100 rounded-3 bg-secondary d-flex justify-content-center align-items-center flex-column">
        <Display :resultado="props.resultado" />
        <Form
            :setValor1="props.setValor1"
            :setOperacao="props.setOperacao"
            :setValor2="props.setValor2"
            :resetFields="props.resetFields"
            :setResultado="props.setResultado"
        />
    </main>
</template>
