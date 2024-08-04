<script setup>
import { ref } from "vue";

const tasks = ref(["tidur", "makan", "mandi"]);

const input = ref("");

const addTask = () => {
  if (input.value) {
    tasks.value.push(input.value);
    input.value = "";
  }
};
</script>

<template>
  <div class="flex items-center justify-center p-4">
    <div class="text-center">
      <div class="mb-3">
        <input
          type="text"
          autofocus
          class="p-1 border border-black rounded"
          @keyup.enter="addTask()"
          v-model="input"
        />
      </div>
      <div
        v-for="task in tasks"
        :key="task"
        class="p-2 mt-3 border border-black min-w-[640px] rounded"
      >
        <div>{{ task }}</div>
      </div>
    </div>
  </div>
</template>

<style scoped></style>
