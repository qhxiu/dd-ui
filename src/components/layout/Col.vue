<template>
  <div class="d-col" :class="colClassList" :style="`padding: 0 ${gutter/2}px`">
    <slot></slot>
  </div>
</template>

<script>
export default {
  props: {
    span: {},
    xl: { type: Number },
    lg: { type: Number },
    md: { type: Number },
    sm: { type: Number },
    xs: { type: Number }
  },
  inject: ['gutter'],
  computed: {
    colClassList() {
      const classList = [];
      const {span, xl, lg, md, sm, xs} = this;
      if (span) classList.push(`d-col-${span}`);
      if (xl) classList.push(`d-col-xl-${xl}`);
      if (lg) classList.push(`d-col-lg-${lg}`);
      if (md) classList.push(`d-col-md-${md}`);
      if (sm) classList.push(`d-col-sm-${sm}`);
      if (xs) classList.push(`d-col-xs-${xs}`);
      return classList;
    }
  }
};
</script>

<style lang="scss" scoped>
.d-col {
  float: left;
  box-sizing: border-box;
}
@for $i from 1 through 24 {
  $d-col: d-col-;
  .#{$d-col}#{$i} {
    width: 1/24 * $i * 100%;
  }
}
@media screen and (max-width: 576px) {
  $d-col-xs-prefix: d-col-xs-;
  @for $i from 1 through 24 {
    .#{$d-col-xs-prefix}#{$i} {
      width: 1/24 * $i * 100%
    }
  }
}
@media screen and (min-width: 576px) and (max-width: 768px) {
  $d-col-sm-prefix: d-col-sm-;
  @for $i from 1 through 24 {
    .#{$d-col-sm-prefix}#{$i} {
      width: 1/24 * $i * 100%
    }
  }
}
@media screen and (min-width: 768px) and (max-width: 992px) {
  $d-col-md-prefix: d-col-md-;
  @for $i from 1 through 24 {
    .#{$d-col-md-prefix}#{$i} {
      width: 1/24 * $i * 100%
    }
  }
}
@media screen and (min-width: 992px) and (max-width: 1200px) {
  $d-col-lg-prefix: d-col-lg-;
  @for $i from 1 through 24 {
    .#{$d-col-lg-prefix}#{$i} {
      width: 1/24 * $i * 100%
    }
  }
}
@media screen and (min-width: 1200px) {
  $d-col-xl-prefix: d-col-xl-;
  @for $i from 1 through 24 {
    .#{$d-col-xl-prefix}#{$i} {
      width: 1/24 * $i * 100%
    }
  }
}
</style>
