<script setup>

defineProps({
    label: String,
    iconClasses: String
})

</script>

<template>
    <button @click=registerUser class="
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
        <span> {{ label }}</span>
    </button>
</template>