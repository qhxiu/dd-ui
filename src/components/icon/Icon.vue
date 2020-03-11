<template>
  <svg class="d-icon" aria-hidden="true" :style="{ color }">
    <use :xlink:href="`#i-${name}`"></use>
  </svg>
</template>

<script>
import "./svg.js";
export default {
  name: "d-icon",
  props: ["name", "color"]
};
</script>

<style lang="scss" scoped>
.d-icon {
  width: 1em;
  height: 1em;
  fill: currentColor;
  overflow: hidden;
}
.loading {
  animation: loading 1s infinite linear;
}
@keyframes loading {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}
</style>
