<script setup>
const props = defineProps(['setValor1', 'setOperacao', 'setValor2', 'setResultado', 'resetFields']);
</script>

<template>
    <form class="ms-3 me-3 mb-3" @submit.prevent="props.setResultado">
        <div class="row g-1">
            <div class="col-4">
                <input
                    @keyup="setValor1"
                    class="form-control w-100 fs-2 text-center"
                    type="number"
                    placeholder="Valor"
                />
            </div>
            <div class="col-4">
                <select @change="setOperacao" class="form-select w-100 fs-2">
                    <option value="soma" selected>➕</option>
                    <option value="subtracao">➖</option>
                    <option value="multiplicacao">✖️</option>
                    <option value="divisao">➗</option>
                </select>
            </div>
            <div class="col-4">
                <input
                    @keyup="setValor2"
                    class="form-control w-100 fs-2 text-center text-center"
                    type="number"
                    placeholder="Valor"
                />
            </div>
            <div class="col-2"></div>
        </div>
        <div class="row g-1">
            <div class="col"></div>
            <div class="col-3 mt-3">
                <button @click="resetFields" class="btn btn-danger w-100 fs-2" type="reset">C</button>
            </div>
        </div>
    </form>
</template>
