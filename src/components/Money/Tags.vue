<template>
  <div class="tags">
    <ul class="current">
      <li v-for="tag in dataSource" :key="tag"
          :class="{selected:selectedTags.indexOf(tag)>=0}"
          @click="select(tag)">
        <div class="tags-icon">
          <Icon name="repast"/>
          {{tag}}
        </div>
      </li>
    </ul>
  </div>
</template>
<script lang="ts">
import Vue from 'vue';
import {Component, Prop} from 'vue-property-decorator';

@Component
export default class Tags extends Vue {
  @Prop(Array) dataSource: string[] | undefined;
  selectedTags: string[] = [];
  select(tag:string){
    this.selectedTags.push(tag);
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
        &.selected{
          background: #B6C7A2;
        }
        //> .icon {
        //  width: 48px;
        //  height: 48px;
        //}
      }
    }
  }
}
</style>