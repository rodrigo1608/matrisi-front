<script setup>
import { ref } from 'vue'

// Variaveis reativas para os campos do formulario
const job = ref({
    title: '',
    description: '',
    modality: '',
    contractType: '',
    date: ''
})

const submitForm = () => {
    // Aqui é onde você faria a requisição POST para a sua API
    // Por enquanto, vamos apenas logar os dados no console
    console.log('Formulario enviado!', job.value);
}
</script>

<template>

    <form action="">
        <input type="text" name="firstName">
    </form>

</template>