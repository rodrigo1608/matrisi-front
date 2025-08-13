<script setup>

import { ref, computed } from 'vue'
import Aside from '@/layouts/Aside.vue'
import Header from './layouts/Header.vue'
import Main from './layouts/Main.vue'

const isAsideOpen = ref(false)
const toggleAside = () => isAsideOpen.value = !isAsideOpen.value

const currentEntity = ref('Users');
const updateEntity = (selectedEntity) => currentEntity.value = selectedEntity

</script>

<template>

  <div class="
  flex
  flex-col 
  md:flex-row 
  min-h-screen
  max-h-screen
  ">

    <Header :toggle-aside="toggleAside" class="md:hidden" />

    <Aside :is-aside-open="isAsideOpen" :toggle-aside="toggleAside" @emited-entity="updateEntity" />

    <div class="
    flex 
    flex-col 
    h-full 
    w-full 
    border 
    border-8 
    border-blue">
      <Header :toggle-aside="toggleAside" class="hidden md:block" />

      <!-- Película: escurece o fundo quando aside estiver aberto (mobile) -->
      <div v-if="isAsideOpen" class="
      fixed 
      top-16 
      inset-0 
      z-20 
      bg-edarker 
      opacity-50 
      md:hidden
      " @click="toggleAside" />

      <Main :currentEntity="currentEntity" :is-aside-open="isAsideOpen" />
    </div>


  </div>

</template>
