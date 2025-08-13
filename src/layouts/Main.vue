<script setup>

import Organizations from '@/Organizations.vue'
import Users from '@/Users.vue'
import UserForm from '@/forms/UserForm.vue'

const componentMap = {
    'Users': Users,
    'Organizations': Organizations,
    'Organizations': Organizations,
    'UserForm': UserForm,
}

defineProps({
    'currentEntity': String,
    'isAsideOpen': Boolean
})

</script>

<template>
    <main class="
    flex-1
    border
    border-8    
    py-4
    px-2
    ">

        <div class="
        md:w-3/5 
        transition-[margin] 
        duration-300
        " :class="[isAsideOpen ?
            'md:mr-64' :
            'md:mr-24']
            ">
            <keep-alive>
                <!-- <component :is="componentMap[currentEntity]" /> -->
            </keep-alive>
        </div>

    </main>
    <!-- <component :is="componentMap['UserForm']" :is-aside-open="isAsideOpen" /> -->

</template>