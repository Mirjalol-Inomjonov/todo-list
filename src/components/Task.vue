<template>
  <div
    @dblclick="$emit('toggle-reminder', task.id)"
    :class="[task.reminder ? 'reminder' : '', 'task']"
  >
    <h3>
      {{ task.text }}
      <i @click="onRemove(task.id)" class="fas fa-times"></i>
    </h3>
    <p>{{ task.day }}</p>
  </div>
</template>

<script>
export default {
  name: "Task",
  props: {
    task: Object,
  },
  methods: {
    onRemove(id) {
      this.$emit("remove-task", id);
    },
  },
};
</script>

<style lang="scss" scoped>
.task {
  background: #f4f4f4;
  margin: 5px;
  padding: 10px 20px;
  cursor: pointer;
  border-left: 5px solid transparent;
  &.reminder {
    border-left-color: lightgreen;
  }
  h3 {
    display: flex;
    align-items: center;
    justify-content: space-between;
    .fas {
      color: red;
    }
  }
}
</style>
