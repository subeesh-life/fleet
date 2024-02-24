<template>
  <lord-icon :src="iconUrl" trigger="loop" stroke="bold" colors="secondary:blue,primary:red" state="loop-roll"
    :style="iconStyle">
  </lord-icon>
</template>

<script>
export default {
  props: {
    iconUrl: String,
    size: {
      type: [String, Number],
      default: 24,
    },
  },
  computed: {
    iconStyle() {
      const sizeValue =
        typeof this.size === 'number' ? `${this.size}px` : this.size;
      return {
        width: sizeValue,
        height: sizeValue,
      };
    },
  },
};
</script>
