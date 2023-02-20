<template>
  <div>
    <Layout class-prefix="layout">
      {{ record }}
      <NumberPad @update:value="onUpdateAmount" />
      <Notes @update:value="onUpdateNotes" />
      <Tags :data-source.sync="tags" @update:value="onUpdateTags" />
      <Types :value.sync="record.type" />
    </Layout>
  </div>
</template>
<script lang="ts">
import Vue from "vue";
import NumberPad from "@/components/Money/NumberPad.vue";
import Notes from "@/components/Money/Notes.vue";
import Tags from "@/components/Money/Tags.vue";
import Types from "@/components/Money/Types.vue";
import { Component } from "vue-property-decorator";

type Record = {
  // eslint-disable-next-line @typescript-eslint/ban-types
  tags: object[];
  notes: string;
  type: string;
  amount: number;
};
@Component({
  components: { Types, Tags, Notes, NumberPad },
})
export default class Money extends Vue {
  tags = [
    { name: "餐饮", svgName: "repast" },
    { name: "医疗", svgName: "medical" },
    { name: "购物", svgName: "shopping" },
    { name: "住宿", svgName: "house" },
    { name: "学习", svgName: "learning" },
    { name: "娱乐", svgName: "amusement" },
    { name: "化妆", svgName: "dressing" },
    { name: "旅游", svgName: "travel" },
    { name: "交通", svgName: "traffic" },
    { name: "其他", svgName: "other" },
  ];
  record: Record = {
    tags: [],
    notes: "",
    type: "-",
    amount: 0,
  };
  // eslint-disable-next-line @typescript-eslint/ban-types
  onUpdateTags(value: object[]) {
    this.record.tags = []
    this.record.tags.push(value.name);

  }
  onUpdateNotes(value: string) {
    this.record.notes = value;
  }
  onUpdateAmount(value: string) {
    this.record.amount = parseFloat(value);
  }
}
</script>
<style lang="scss">
.layout-content {
  display: flex;
  flex-direction: column-reverse;
}
</style>
<style lang="scss" scoped>

</style>
