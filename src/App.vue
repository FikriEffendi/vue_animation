<script setup>
import { RouterLink, RouterView } from "vue-router";
</script>

<template>
  <div class="flex justify-center py-3 my-2">
    <div
      class="flex divide-x justify-center items-center border rounded-lg w-[300px]"
    >
      <router-link to="/" class="px-4 py-2">Home</router-link>
      <router-link to="/about" class="px-4 py-2">About</router-link>
    </div>
  </div>

  <Transition name="route">
    <RouterView />
  </Transition>
</template>

<style scoped>
.route-enter-from,
.route-leave-to {
  @apply -translate-x-8 opacity-0;
}

.route-enter-to,
.route-leave-from {
  @apply opacity-100 translate-x-0;
}

.route-enter-active,
.route-move {
  @apply transition-all duration-200 ease-in;
}

.route-leave-active {
  @apply transition-all duration-200 ease-in absolute;
}
</style>
