<template>
  <div class="numberPad">
    <div class="output">
      <div class="number">0</div>
    </div>
    <div class="buttons clearfix">
      <button>1</button>
      <button>2</button>
      <button>3</button>
      <button>+</button>
      <button>4</button>
      <button>5</button>
      <button>6</button>
      <button>-</button>
      <button>7</button>
      <button>8</button>
      <button>9</button>
      <button class="ok">OK</button>
      <button>0</button>
      <button>.</button>
      <button class="delete">
        <icon name="delete"></icon>
      </button>
    </div>
  </div>
</template>
<script lang="ts">
export default {
  name: 'NumberPad'
};
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
  }
  .buttons {
    background: $color-highlight;
    border-radius: 6%;
    @extend %clearFix;
    >button {
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