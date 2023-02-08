<template>
  <div>
    <Layout class-prefix="layout">
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
      <div>
        <label class="notes">
          <span class="name">备注</span>
          <input type="text" placeholder="这里写备注~">
        </label>
      </div>
      <div class="tags">
        <ul class="current">
          <li>
            <div class="tags-icon">
              <Icon name="repast" />
            </div>
            <span>餐饮</span>
          </li>
          <li>
            <div class="tags-icon">
              <Icon name="medical" />
            </div>
            <span>医疗</span>
          </li>
          <li>
            <div class="tags-icon">
              <Icon name="shopping" />
            </div>
            <span>购物</span>
          </li>
          <li>
            <div class="tags-icon">
              <Icon name="traffic" />
            </div>
            <span>交通</span>
          </li>
          <li>
            <div class="tags-icon">
              <Icon name="house" />
            </div>
            <span>住宿</span>
          </li>
          <li>
            <div class="tags-icon">
              <Icon name="learning" />
            </div>
            <span>学习</span>
          </li>
          <li>
            <div class="tags-icon">
              <Icon name="amusement" />
            </div>
            <span>娱乐</span>
          </li>
          <li>
            <div class="tags-icon">
              <Icon name="dressing" />
            </div>
            <span>化妆</span>
          </li>
          <li>
            <div class="tags-icon">
              <Icon name="travel" />
            </div>
            <span>旅游</span>
          </li>
          <li>
            <div class="tags-icon">
              <Icon name="add" />
            </div>
            <span>添加</span>
          </li>
        </ul>
      </div>
      <div>
        <ul class="types">
          <li class="selected">支出</li>
          <li>收入</li>
        </ul>
      </div>
    </Layout>
  </div>
</template>

<script lang="ts">
export default {
  name: 'Money.vue',
};
</script>
<style lang="scss">
.layout-content {
  display: flex;
  flex-direction: column-reverse;
}
</style>

<style lang="scss" scoped>
@import "~@/assets/style/helper.scss";

.types {
  background: $color-highlight;
  display: flex;
  text-align: center;
  font-size: 20px;

  >li {
    width: 50%;
    height: 64px;
    display: flex;
    justify-content: center;
    align-items: center;
    position: relative;

    &.selected::after {
      content: '';
      position: absolute;
      bottom: 0;
      left: 0;
      width: 100%;
      height: 2px;
      background: #333;
    }
  }
}

;

.tags {
  flex-grow: 1;

  >.current {
    display: flex;
    flex-wrap: wrap;
    flex-direction: row;
    align-content: center;
    overflow: auto;

    >li {
      display: flex;
      width: 25%;
      padding: 12px 0;
      flex-direction: column;
      align-items: center;
      font-size: 12px;

      >.tags-icon {
        display: flex;
        width: 48px;
        height: 48px;
        padding: 4px;
        border-radius: 50%;
        background: #f5f5f5;
        margin-bottom: 4px;
        justify-content: center;
        align-items: center;

        >.icon {
          width: 48px;
          height: 48px;
        }
      }
    }
  }
}

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