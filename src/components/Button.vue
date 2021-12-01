<template>
  <div>
    <button @click="onClick()" class="btn" :style="{ background: color }">{{ text }}</button>
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
    onClick(){
      console.log('kbcdhj');
    }
  },
};
</script>

<style lang="scss" scoped></style>
