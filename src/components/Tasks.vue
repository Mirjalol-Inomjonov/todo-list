<template>
  <div>
    <div v-for="task in tasks" :key="task.id">
      <Task @remove-task="$emit('remove-task', task.id)" :task="task" />
    </div>
  </div>
</template>

<script>
import Task from "./Task.vue";
export default {
  components: { Task },
  name: "Tasks",
  props: {
    tasks: Array,
  },
  emits: ["remove-task"],
};
</script>

<style lang="scss" scoped></style>
