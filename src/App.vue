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

  <RouterView />
</template>
