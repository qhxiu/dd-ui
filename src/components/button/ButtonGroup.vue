<template>
  <div class="btn-group">
    <slot></slot>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.btn-group {
  display: inline-block;
  vertical-align: middle;
  > .d-button {
    border-radius: 0;

    &:not(:last-child) {
      margin-right: -1px;
    }
    &:not(:first-child),
    &:not(:last-child) {
      border-left-color: $borderColor;
      border-right-color: $borderColor;
    }
    &:first-child {
      border-top-left-radius: $borderRadius;
      border-bottom-left-radius: $borderRadius;
    }
    &:last-child {
      border-top-right-radius: $borderRadius;
      border-bottom-right-radius: $borderRadius;
    }
    &.d-button-primary {
      &:first-child {
        border-right-color:#ccc;
      }
      &:last-child {
        border-left-color: #ccc;
      }
    }
  }
}
</style>
