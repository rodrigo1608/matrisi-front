<script setup>

import { ref } from 'vue'
import Aside from '@/layouts/Aside.vue'
import Header from './layouts/Header.vue'
import Main from './layouts/Main.vue'

const isAsideOpen = ref(false)
const toggleAside = () => isAsideOpen.value = !isAsideOpen.value

const currentEntity = ref('Users');
const updateEntity = (selectedEntity) => currentEntity.value = selectedEntity

</script>

<template>
  <div class="flex flex-col md:flex-row min-h-screen max-h-screen">

    <Header :toggle-aside="toggleAside" class="md:hidden" />

    <Aside :is-aside-open="isAsideOpen" :toggle-aside="toggleAside" @emited-entity="updateEntity" />

    <div class="flex flex-col w-full">
      <Header :toggle-aside="toggleAside" class="hidden md:block" />

      <Main :currentEntity="currentEntity" class="flex-grow overflow-auto" />
    </div>

  </div>
</template>
