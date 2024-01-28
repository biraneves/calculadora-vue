<script setup>
const props = defineProps(['resultado']);
</script>

<template>
    <div class="m-3 p-3 display rounded-2 d-flex justify-content-center align-items-center flex-column">
        <p class="calculator m-0">{{ props.resultado }}</p>
    </div>
</template>

<style scoped>
@font-face {
    font-family: 'Calculator';
    src: url(../assets/font/Calculator.ttf) format('truetype');
}

.display {
    background-color: rgb(33, 42, 33);
    color: rgb(27, 249, 90);
    min-width: 90%;
}

.calculator {
    font-family: 'Calculator', sans-serif;
    font-size: 40px;
    letter-spacing: 4px;
    display: block;
    text-align: right;
    width: 98%;
}

@media screen and (min-width: 768px) {
    .calculator {
        font-size: 64px;
    }
}
</style>
