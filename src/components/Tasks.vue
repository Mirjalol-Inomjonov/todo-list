<template>
  <div>
    <div v-for="task in tasks" :key="task.id">
      <Task :task="task" />
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
};
</script>

<style lang="scss" scoped></style>
