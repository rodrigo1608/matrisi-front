<script setup>
import Avatar from '@/Avatar.vue';
import MenuButton from '@/MenuButton.vue';

defineProps({
    'toggleAside': {
        type: Function,
        required: true
    }
})

</script>

<template>

    <header class="h-16 ">

        <nav class="flex h-full justify-between items-center bg-yellow-300">
            <MenuButton @toggle="toggleAside" class="md:hidden" />
            <a href="#" class="font-[Crimson_Pro] text-gray-500 text-lg tracking-wider font-semibold">Matrisi</a>
            <Avatar />
        </nav>

    </header>

</template>