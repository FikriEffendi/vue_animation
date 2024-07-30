<script setup>
import { ref } from 'vue';


const showText=ref('true');
</script>

<template>
  <main>
    <transition name="fade">
      <h1 v-if="showText">Halo banh!</h1>
    </transition>
    <button @click="showText=!showText">toggle</button>
  </main>
</template>

<style scoped>
.fade-enter-from,
.fade-leave-to{
  @apply opacity-0 ;
}

.fade-enter-to,
.fade-leave-from{
  @apply opacity-100;
}

.fade-enter-active{
  @apply transition-all duration-1000 ease-in; 
}

.fade-leave-active{
  @apply transition-all duration-1000 ease-out;
}
</style>