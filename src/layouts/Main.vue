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
    py-4
    px-2  
    flex-1
    max-h-full   
    ">
        <div class="        
        md:w-3/5 
        transition-[margin] 
        duration-300
        h-full
        overflow-y-auto
        mx-auto
        max-h-[calc(100%-4rem)]  
        " :class="[isAsideOpen ?
            'md:ml-64' :
            'md:ml-24']
            ">
            <keep-alive>
                <component :is="componentMap[currentEntity]" />
            </keep-alive>
        </div>

    </main>
    <!-- <component :is="componentMap['UserForm']" :is-aside-open="isAsideOpen" /> -->

</template>