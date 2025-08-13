<script setup>
import Avatar from '@/buttons/Avatar.vue';
import MenuButton from '@/buttons/MenuButton.vue';

defineProps({
    'toggleAside': {
        type: Function,
        required: true
    }
})

</script>

<template>

    <header class="
        h-16 
        px-4 
        w-full
        ">
        <nav class="
            flex 
            h-full 
            justify-between 
            items-center
            ">
            <MenuButton @toggle="toggleAside" class="md:hidden" />

            <a href="#" class="
            font-[Crimson_Pro] 
            text-gray-500 
            text-lg 
            tracking-wider 
            font-semibold
            ">
                Matrisi
            </a>
            <Avatar />
        </nav>

    </header>

</template>