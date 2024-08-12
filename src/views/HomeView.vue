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

const deleteTask = (deletedTask) => {
  tasks.value = tasks.value.filter((task) => task !== deletedTask);
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
      <transition-group name="list">
        <div
          v-for="task in tasks"
          :key="task"
          class="mt-3 min-w-[640px] cursor-pointer"
          @click="deleteTask(task)"
        >
          <div class="px-1 py-3 bg-gray-100 rounded shadow">{{ task }}</div>
        </div>
      </transition-group>
    </div>
  </div>
</template>

<style scoped>
.list-enter-from,
.list-leave-to {
  @apply opacity-0 scale-50;
}

.list-enter-to,
.list-leave-from {
  @apply opacity-100 scale-100;
}

.list-enter-active,
.list-leave-active {
  @apply transition-all duration-200 ease-in;
}
</style>
