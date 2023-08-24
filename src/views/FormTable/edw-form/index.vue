<template>
  <div class="at-form--search">
    <component v-for="item in formConfig" :key="item.id" v-bind:is="item.type" 
      v-on="$listeners" :configData="item"></component>
    <!-- 自定义组件 -->
    <!-- 时间选择器 -->
    <slot name="timePicker"></slot>
    <!-- 日期选择器 -->
    <slot name="datePicker"></slot>
    <!-- 日期时间选择器 -->
    <slot name="dateTimePicker"></slot>
    <!-- 默认插槽 -->
    <slot></slot>
  </div>
</template>
<script>
import RadioGroup from "./components/RadioGroup.vue";
import CheckboxGroup from "./components/CheckboxGroup.vue";
import Input from "./components/Input.vue";
import Select from "./components/Select.vue";
import Cascader from "./components/Cascader.vue";
import Switch from "./components/Switch.vue";
export default {
  name: "AvlForm",
  data() {
    return {};
  },
  props: {
    formConfig: {
      type: Array,
      required: true
    }
  },
  components: {
    "edw-radio": RadioGroup,
    "edw-checkbox": CheckboxGroup,
    "edw-input": Input,
    "edw-select": Select,
    "edw-cascader": Cascader,
    "edw-switch": Switch
  }
};
</script>

<style>
.at-form--search {
  display: flex;
  align-items: center;
  flex-wrap: wrap;
}

.at-form-component:not(:last-child) {
  margin-right: 10px;
}

.at-form-component {
  margin-bottom: 10px;
}
</style>