<template>
  <button class="d-button" :class="btnClass">
    <d-icon v-if="icon && iconPosition==='left' && !loading" :name="icon" :class="`${iconPosition}-icon`"></d-icon>
    <d-icon v-if="loading" name="loading" :class="`${iconPosition}-icon loading`"></d-icon>
    <div class="btn-c">
      <slot></slot>
    </div>
    <d-icon v-if="icon && iconPosition==='right' && !loading" :name="icon" :class="`${iconPosition}-icon`"></d-icon>
  </button>
</template>

<script>
import Icon from '../icon/Icon.vue'
export default {
  components: {
    DIcon: Icon
  },
  props: {
    'type': {
      type: String,
      validator(val) {
        return ["primary", "info", "success", "warning", "danger"].includes(
          val
        );
      }
    },
    'disabled': {
      type: Boolean,
      default: false
    },
    'icon': {
      type: String,
      default: ''
    },
    'iconPosition': {
      type: String,
      default: 'left',
      validator(val) {
        return val === 'left' || val === 'right'
      }
    },
    'loading' : {
      type: Boolean,
      default: false
    }
  },
  computed: {
    btnClass() {
      const classList = [];
      if (this.type)  classList.push(`d-button-${this.type}`);
      if (this.disabled) classList.push(`d-button-disabled`);
      return classList.join(" ");
    }
  }
};
</script>

<style lang="scss">
// @import "../../assets/scss/variables.scss";
.d-button {
  min-width: 70px;
  height: 32px;
  line-height: 32px;
  border: 1px solid $borderColor;
  padding: 0 1em;
  border-radius: 4px;
  font-size: $fontSize;
  vertical-align: middle;
  display: inline-flex;
  justify-content: center;
  align-items: center;
  &:focus {
    outline: none;
  }
  &:hover {
    opacity: 0.8;
  }
  &.d-button-primary {
    color: #fff;
    background-color: $primaryColor;
    border-color: $primaryColor;
  }
  &.d-button-info {
    color: #fff;
    background-color: $infoColor;
    border-color: $infoColor;
  }
  &.d-button-success {
    color: #fff;
    background-color: $successColor;
    border-color: $successColor;
  }
  &.d-button-warning {
    color: #fff;
    background-color: $warningColor;
    border-color: $warningColor;
  }
  &.d-button-danger {
    color: #fff;
    background-color: $dangerColor;
    border-color: $dangerColor;
  }
  &.d-button-disabled {
    cursor: not-allowed;
    opacity: 0.7;
    &.hover, &.active {
      opacity: 0.7;
    }
  }
  .left-icon {
    margin-right: .4em;
  }
  .right-icon {
    margin-left: .4em;
  }
}
</style>