<template>
  <t-card :cover="cover" theme="poster2" :style="{ width: '400px' }">
    <template #footer>
      <t-comment avatar="https://tdesign.gtimg.com/site/avatar-boy.jpg" author="标题" content="卡片内容" />
    </template>
    <template #actions>
      <t-dropdown :options="options" :min-column-width="112" @click="clickHandler">
        <t-button variant="text" shape="square">
          <more-icon size="24" />
        </t-button>
      </t-dropdown>
    </template>
  </t-card>
</template>
<script setup lang="jsx">
import { MessagePlugin } from 'tdesign-vue-next';
import { MoreIcon } from 'tdesign-icons-vue-next';

const clickHandler = (data) => {
  MessagePlugin.success(`选中【${data.content}】`);
};
const options = [
  {
    content: '操作一',
    value: 1,
  },
  {
    content: '操作二',
    value: 2,
  },
];
const cover = 'https://tdesign.gtimg.com/site/source/card-demo.png';
</script>
