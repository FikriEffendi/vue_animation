<script setup>
import { RouterLink, RouterView } from "vue-router";
</script>

<template>
  <header class="container">
    <router-link to="/">Home</router-link>
    <router-link to="/about">About</router-link>
  </header>
  <RouterView />
</template>
