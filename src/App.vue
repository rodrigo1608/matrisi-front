<script setup>

import { ref } from 'vue'
// import Aside from '@/layouts/Aside.vue'
// import Header from './layouts/Header.vue'
// import Main from './layouts/Main.vue'





const currentEntity = ref('Users');
const updateEntity = (selectedEntity) => currentEntity.value = selectedEntity

</script>

<template>

  <div class="
  flex
  flex-col 
  md:flex-row
  h-dvh      
  ">

    <Header class="md:hidden" />

    <Aside @emited-entity="updateEntity" />

    <div class="
    flex-1
    flex 
    flex-col
    h-full    
    ">

      <!-- <Header class="hidden md:block" /> -->

      <!-- Película: escurece o fundo quando aside estiver aberto (mobile) -->
      <div v-if="isAsideOpen" class="
      fixed 
      top-16 
      inset-0 
      z-20 
      bg-edarker 
      opacity-50 
      md:hidden      
      " />
      <!-- <Main :currentEntity="currentEntity" :is-aside-open="isAsideOpen" /> -->
      Aqui



    </div>
  </div>

</template>