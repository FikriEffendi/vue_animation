<script setup>
import { ref } from "vue";

const showText = ref("true");
</script>

<template>
  <main>
    <div class="relative">
      <transition name="fade">
        <h1 v-if="showText" key="text-1" class="absolute">Halo banh!</h1>
        <h1 v-else key="text-2" class="absolute">Oke</h1>
      </transition>
      <button @click="showText = !showText" class="mt-3">toggle</button>
    </div>
  </main>
</template>

<style scoped>
.fade-enter-from,
.fade-leave-to {
  @apply opacity-0;
}

.fade-enter-to,
.fade-leave-from {
  @apply opacity-100;
}

.fade-enter-active,
.fade-leave-active {
  @apply transition-all duration-1000 ease-in-out;
}
</style>
