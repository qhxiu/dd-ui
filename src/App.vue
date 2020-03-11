<template>
  <div id="app">
    <d-button loading icon="loading" type="primary">加载中</d-button>
    <d-button-group>
      <d-button type="primary" icon="left" icon-position="left">rev</d-button>
      <d-button type="primary">middle</d-button>
      <d-button type="primary" icon="right" icon-position="right"
        >next</d-button
      >
    </d-button-group>

    <d-row gutter="20">
      <d-col :xl="12" :lg="3" :sm="9">111</d-col>
      <d-col :xl="4" :lg="9" :sm="3">2222</d-col>
      <d-col :xl="2" :lg="9" :sm="3">333</d-col>
      <d-col :xl="6" :lg="3" :sm="9">444</d-col>
    </d-row>
  </div>
</template>
<script>
import Icon from "./components/icon/Icon.vue";
import Button from "./components/button/Button.vue";
import ButtonGroup from "./components/button/ButtonGroup.vue";
import Row from "./components/layout/Row.vue";
import Col from "./components/layout/Col.vue";
export default {
  components: {
    DIcon: Icon,
    DButton: Button,
    DButtonGroup: ButtonGroup,
    DRow: Row,
    DCol: Col
  },
  data() {
    return {};
  }
};
</script>
<style></style>
