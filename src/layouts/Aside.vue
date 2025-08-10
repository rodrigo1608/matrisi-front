<script setup>
import { computed, ref, onUpdated } from 'vue'
import MenuButton from '@/MenuButton.vue'
import AsideNavigation from '@/AsideNavigation.vue'

const props = defineProps({
    'isAsideOpen': { type: Boolean, default: false },
    'toggleAside': Function
})

// Define as classes para a versão desktop, que empurra o conteúdo
const asideDesktopClasses = computed(() => {
    return [
        'h-full', 'bg-elight', 'transition-all', 'duration-300', 'p-4',
        'hidden md:block',
        props.isAsideOpen ? 'md:w-60' : 'md:w-22',
        props.isAsideOpen ? 'md:overflow-auto' : 'md:overflow-hidden'
    ]
})

// Define a lista de navegação
const navigationItems = ref([
    { name: 'Users', href: '#', icon: 'fa-solid fa-users' },
    { name: 'Organizations', href: '#', icon: 'fa-solid fa-building' },

]);

const selectedComponent = ref('');
const emit = defineEmits(['emitedEntity'])

const emitSelectedEntity = (selectedEntity) => emit('emitedEntity', selectedEntity)

</script>

<template>
    <!-- Versão Mobile (com animação de deslizar) -->
    <Transition name="slide">
        <aside v-if="isAsideOpen" class="md:hidden h-dvh bg-elight w-full transition-transform duration-300 transform">
            <AsideNavigation :navigation-items="navigationItems" :is-aside-open="props.isAsideOpen"
                @select-entity="emitSelectedEntity" />
        </aside>
    </Transition>

    <!-- Versão Desktop (com animação de largura) -->
    <aside :class="asideDesktopClasses">
        <MenuButton @toggle="toggleAside" />
        <AsideNavigation :navigation-items="navigationItems" :is-aside-open="props.isAsideOpen"
            @select-entity="emitSelectedEntity" />

        {{ selectedComponent }}

    </aside>

</template>

<style scoped>
/* Transição de deslizar para mobile */
.slide-enter-from,
.slide-leave-to {
    transform: translateX(-100%);
}

.slide-enter-to,
.slide-leave-from {
    transform: translateX(0);
}

.slide-enter-active,
.slide-leave-active {
    transition: transform 0.3s ease-in-out;
}
</style>
