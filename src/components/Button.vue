<template>
  <div>
    <button @click="onClick" class="btn" :style="{ background: color }">
      {{ text }}
    </button>
  </div>
</template>

<script>
export default {
  name: "Button",
  props: {
    text: String,
    color: String,
  },
  data() {
    return {};
  },

  methods: {
    onClick() {
      this.$emit("toggle-add-task");
    },
  },
};
</script>

<style lang="scss" scoped></style>
