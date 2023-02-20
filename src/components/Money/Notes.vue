<template>
  <div>
    <label class="notes">
      <span class="name">备注</span>
      <input type="text" v-model="value" placeholder="这里写备注~">
    </label>
  </div>
</template>
<script lang="ts">
import Vue from 'vue';
import { Component, Watch } from 'vue-property-decorator';

@Component
export default class Notes extends Vue {
  value = '';
  @Watch('value')
  onValueChanged(value: string, oldValue: string) {
    this.$emit('update:value', value)
  }
}
</script>
<style scoped lang="scss">
.notes {
  font-size: 14px;
  background: #f5f5f5;
  display: block;
  padding-left: 16px;
  display: flex;
  align-items: center;

  .name {
    padding-right: 16px;
  }
}

input {
  height: 32px;
  flex-grow: 1;
  background: transparent;
  border: none;
  padding-right: 16px;
}
</style>