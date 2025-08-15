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
    flex
    justify-center
    items-center  
    max-h-[calc(100%-4rem)]
    ">
        <div class="  
        w-full
        flex-1
  md:max-w-3/5
        transition-[max-width]  duration-300
        h-full
        overflow-y-auto
        " :class="[isAsideOpen ?
            'md:max-w-[calc(60%+6rem)]' : 'md:max-w-3/5']">
            <keep-alive>
                <component :is="componentMap[currentEntity]" />
            </keep-alive>
        </div>

    </main>
</template>
<!-- <component :is="componentMap['UserForm']" :is-aside-open="isAsideOpen" /> -->