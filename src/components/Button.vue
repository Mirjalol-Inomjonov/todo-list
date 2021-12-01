<template>
  <div>
    <button class="btn" :style="{ background: color }">
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
    
  },
};
</script>

<style lang="scss" scoped></style>
