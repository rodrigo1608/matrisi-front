<script setup>
defineProps({
    input: Object,
    modelValue: String
})
const emit = defineEmits(['update:modelValue'])

const updateValue = (event) => {
    emit('update:modelValue', event.target.value)
}
</script>
<template>

    <div class="">
        <label :for="input.forId" :class="input.labelClasses" class="capitalize">{{ input.name }}</label>
        <input :id="input.forId" :type="input.type" :name="input.name" :class="input.inputClasses" @input="updateValue">
    </div>

</template>
