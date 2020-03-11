<template>
  <div class="d-row" :style="rowMargin">
    <slot></slot>
  </div>
</template>

<script>
export default {
  props: {
    gutter: {
      type: [Number, String]
    }
  },
  computed: {
    rowMargin() {
      const { gutter } = this;
      return `margin-left: ${gutter / 2}px; margin-right: ${gutter / 2}px`;
    }
  },
  provide() {
    return {
      gutter: this.gutter
    };
  }
};
</script>

<style lang="scss" scoped>
.d-row {
  width: 100%;
  overflow: hidden;
}
</style>
