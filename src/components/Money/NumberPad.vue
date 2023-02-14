<template>
  <div class="numberPad">
    <div class="output">{{ output }}</div>
    <div class="buttons clearfix">
      <button @click="inputContent">1</button>
      <button @click="inputContent">2</button>
      <button @click="inputContent">3</button>
      <button @click="add">+</button>
      <button @click="inputContent">4</button>
      <button @click="inputContent">5</button>
      <button @click="inputContent">6</button>
      <button @click="reduce">-</button>
      <button @click="inputContent">7</button>
      <button @click="inputContent">8</button>
      <button @click="inputContent">9</button>
      <button @click="ok" class="ok">OK</button>
      <button @click="inputContent">0</button>
      <button @click="inputContent">.</button>
      <button class="delete" @click="remove">
        <icon name="delete"></icon>
      </button>
    </div>
  </div>
</template>
<script lang="ts">
import Vue from 'vue';
import {Component, Prop} from 'vue-property-decorator';

@Component
export default class NumberPad extends Vue {
  output = '0';

  inputContent(event: MouseEvent) {
    const button = (event.target as HTMLButtonElement);
    const input = button.textContent!;
    if (this.output.length === 16) {
      return;
    }
    if (this.output === '0') {
      if ('0123456789'.indexOf(input) >= 0) {
        this.output = input;
      } else {
        this.output += input;
      }
      return;
    }
    if (this.output.indexOf('.') >= 0 && input === '.') {
      return;
    }
    this.output += input;
  }

  remove() {
    if (this.output.length === 1) {
      this.output = '0';
    } else {
      this.output = this.output.slice(0, -1);
    }
  }
  ok(){
    
  }
  add(){
  }
  reduce(){

  }
}
</script>
<style scoped lang="scss">
@import "~@/assets/style/helper.scss";

.numberPad {
  .output {
    background: #ffffff;
    font-size: 24px;
    font-family: Consolas, monospace;
    padding: 6px 12px;
    text-align: right;
    height: 48px;
  }

  .buttons {
    background: $color-highlight;
    border-radius: 6%;
    @extend %clearFix;

    > button {
      float: left;
      width: 25%;
      height: 56px;
      font-size: 18px;
      background: transparent;
      border: none;

      &.ok {
        height: 56*2px;
        float: right;
      }
    }
  }
}
</style>