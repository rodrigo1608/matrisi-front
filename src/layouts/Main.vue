<script setup>

import Organizations from '@/Organizations.vue'
import Users from '@/Users.vue'


const componentMap = {
    'Users': Users,
    'Organizations': Organizations
}

defineProps({
    'currentEntity': String,
    'isAsideOpen': Boolean
})

</script>

<template>

    <main class="w-full overflow-auto z-10 fixed top-16 bottom-0">

        <div class="m-auto md:w-2/3 ">
            <keep-alive>
                <component :is="componentMap[currentEntity]" />
            </keep-alive>

        </div>

    </main>

</template>