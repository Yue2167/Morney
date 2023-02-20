<template>
  <div class="tags">
    <ul class="current">
      <li v-for="tag in dataSource" :key="tag.name" @click="toggle(tag)">
        <div class="tags-icon" :class="{ selected: selectedTags.indexOf(tag) >= 0 }">
          <Icon :name="tag.svgName"/>
        </div>
        {{ tag.name }}
      </li>
      <li>
        <div class="tags-icon" @click="create">
          <Icon name="add"/>
        </div>
        添加
      </li>
    </ul>
  </div>
</template>
<script lang="ts">
import Vue from 'vue';
import {Component, Prop} from 'vue-property-decorator';

@Component
export default class Tags extends Vue {
  // eslint-disable-next-line @typescript-eslint/ban-types
  @Prop(Array) dataSource: object[] | undefined;
  // eslint-disable-next-line @typescript-eslint/ban-types
  selectedTags: object[] = [];

  // eslint-disable-next-line @typescript-eslint/ban-types
  toggle(tag: object) {
    this.selectedTags = [];
    this.selectedTags.push(tag);
    this.$emit('update:value', this.selectedTags[0]);
  }

  create() {
    let name = window.prompt('请输入四字以下的标签名')!;
    this.dataSource!.forEach(item => {
      console.log(item.name);
      if (item.name == name) {
        name = '';
      }
    });
    if (name.trim() === '' || name.length > 4) {
      alert('标签名不规范或重复命名');
    } else if (this.dataSource) {
      this.$emit('update:dataSource', [
        ...this.dataSource,
        {name, svgName: 'star'},
      ]);
    }
  }
}
</script>
<style scoped lang="scss">
.tags {
  flex-grow: 1;

  > .current {
    display: flex;
    flex-wrap: wrap;
    flex-direction: row;
    align-content: center;
    overflow: auto;

    > li {
      display: flex;
      width: 25%;
      padding: 12px 0;
      flex-direction: column;
      align-items: center;
      font-size: 12px;

      > .tags-icon {
        display: flex;
        flex-direction: column;
        width: 48px;
        height: 48px;
        padding: 4px;
        border-radius: 50%;
        background: #f5f5f5;
        margin-bottom: 4px;
        justify-content: center;
        align-items: center;

        &.selected {
          background: #b6c7a2;
        }

        > .icon {
          width: 48px;
          height: 48px;
        }
      }
    }
  }
}
</style>
