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

    <header class="h-16 px-4 fixed z-40 md:z-0 top-0 w-full md-block">

        <nav class="flex h-full justify-between items-center">
            <MenuButton @toggle="toggleAside" class="md:hidden" />
            <a href="#" class="font-[Crimson_Pro] text-gray-500 text-lg tracking-wider font-semibold">Matrisi</a>
            <Avatar />
        </nav>

    </header>

</template>