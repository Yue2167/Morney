<template>
  <div>
    <Layout class-prefix="layout">
      <NumberPad />
      <Notes />
      <Tags :data-source="tags" />
      <Types />
    </Layout>
  </div>
</template>
<script lang="ts">
import NumberPad from '@/components/Money/NumberPad.vue';
import Notes from '@/components/Money/Notes.vue';
import Tags from '@/components/Money/Tags.vue';
import Types from '@/components/Money/Types.vue';
export default {
  name: 'Money.vue',
  components: { Types, Tags, Notes, NumberPad },
  data() {
    return {
      tags: ['餐饮', '医疗', '购物', '交通', '住宿', '学习', '娱乐', '化妆', '旅游', '添加']

    }
  }
};
</script>
<style lang="scss">
.layout-content {
  display: flex;
  flex-direction: column-reverse;
}
</style>
<style lang="scss" scoped>

</style>