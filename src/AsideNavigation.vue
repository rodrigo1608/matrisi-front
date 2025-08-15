<script setup>

defineProps({
    'navigationItems': {
        type: Array,
        required: true,
        validator: (value) => {
            return value.every(item => {
                return (
                    typeof item.name === 'string' &&
                    typeof item.href === 'string' &&
                    typeof item.icon === 'string'
                )
            })
        }
    },
    'isAsideOpen': Boolean
})

const emit = defineEmits(['selectEntity'])

</script>

<template>
    <nav class="mt-4">
        <ul>
            <li v-for="item in navigationItems" :key="item.name" class="
            border-b-1 
            md:border-none 
            border-egray
            ">

                <a :href="item.href" @click.prevent="emit('selectEntity', item.name)" class="flex 
                    gap-1
                    p-4 
                    md:p-0 
                    md:px-4 
                    md:rounded-full 
                    hover:bg-egray  
                    active:scale-99 
                    active:bg-elighter">

                    <div class="w-6 h-6 flex justify-center mt-2">
                        <i :class="item.icon" class="
                        text-center 
                        text-sm 
                        leading-none"></i>
                    </div>

                    <span class="
                        flex 
                        justify-center 
                        items-center 
                        overflow-ellipsis 
                        pt-2 leading-none 
                        p-0 m-0 
                        whitespace-nowrap
                      " :class="isAsideOpen ? 'inline-block' : 'hidden'">
                        {{ item.name }}
                    </span>
                </a>

            </li>
        </ul>
    </nav>
</template>