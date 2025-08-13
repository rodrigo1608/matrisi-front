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
    w-full
    border
    border-8
    flex
    flex-column 
    justify-center
    items-center
    z-10 
    fixed 
    top-16     
    py-4 
    px-2
    flex-1 
    bg-red-600
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