<script setup>

defineProps({
    label: String,
    ariaLabel: {
        type: String,
        required: true
    },
    iconClasses: String,

})

const emit = defineEmits(['click'])
const buttonClick = () => emit('click')

</script>

<template>
    <button @click="buttonClick" :aria-label=ariaLabel class="
    bg-edark-gray 
    text-elight px-4 py-2 
    text-sm font-medium 
    rounded-full 
    hover:bg-edark 
    cursor-pointer 
    active:scale-99 
    active:bg-edarker   
    capitalize
    flex
    gap-2
    items-center
    jutify-center">

        <i :class="iconClasses"></i>
        <span class="hidden md:inline-block"> {{ label }}</span>
    </button>
</template>