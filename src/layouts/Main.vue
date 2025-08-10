<script setup>

import Organizations from '@/Organizations.vue'
import Users from '@/Users.vue'


const componentMap = {
    'Users': Users,
    'Organizations': Organizations
}

defineProps({
    'currentEntity': String
})

</script>

<template>
    <main class="w-full overflow-auto">
        <div class="m-auto sm:w-2/3 bg-red-500">
            <keep-alive>
                <component :is="componentMap[currentEntity]" />
            </keep-alive>
            <Organizations />
            <Organizations />
            <Organizations />
            <Organizations />
            <Organizations />
            <Organizations />
            <Organizations />
            <Organizations />
            <Organizations />
            <Organizations />
        </div>

    </main>
</template>