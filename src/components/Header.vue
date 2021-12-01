<template>
  <header>
    <h1>
      {{ title }}
    </h1>
      <Button :text="text" :color="color"/>
  </header>
</template>

<script>
import Button from "./Button.vue";
export default {
  components: { Button },
  name: "Header",

  props: {
    title: String,
  },

  data() {
    return {
      text: "Add Task",
      color: "green",
    };
  },
};
</script>

<style lang="scss" scoped>
header {
  display: flex;
  align-content: center;
  justify-content: space-between;
  margin-bottom: 20px;
}
</style>
