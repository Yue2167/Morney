<template>
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
</template>
<script lang="ts">
export default {
  name: 'Tags'
};
</script>
<style scoped lang="scss">
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
</style>