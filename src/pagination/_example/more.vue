<template>
  <t-space direction="vertical">
    <t-space direction="vertical">
      <span>展示首尾页码省略</span>
      <t-pagination
        v-model="current"
        v-model:pageSize="pageSize"
        :total="100"
        @change="onChange"
        @page-size-change="onPageSizeChange"
        @current-change="onCurrentChange"
      />
    </t-space>
    <t-space direction="vertical">
      <span>不展示首尾页码省略</span>
      <t-pagination
        v-model="current"
        v-model:pageSize="pageSize"
        :total="100"
        page-ellipsis-mode="both-ends"
        @change="onChange"
        @page-size-change="onPageSizeChange"
        @current-change="onCurrentChange"
      />
    </t-space>
  </t-space>
</template>

<script setup>
import { ref } from 'vue';
import { MessagePlugin } from 'tdesign-vue-next';

const current = ref(12);
const pageSize = ref(5);

const onPageSizeChange = (size) => {
  console.log('page-size:', size);
  MessagePlugin.success(`pageSize变化为${size}`);
};

const onCurrentChange = (index, pageInfo) => {
  MessagePlugin.success(`转到第${index}页`);
  console.log(pageInfo);
};

const onChange = (pageInfo) => {
  console.log(pageInfo);
};
</script>
<style lang="less">
.t-space {
  width: 100%;
  &-item {
    width: 100%;
  }
}
</style>
