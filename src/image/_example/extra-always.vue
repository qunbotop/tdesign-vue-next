<template>
  <t-space :size="32">
    <t-space direction="vertical">
      <strong :style="{ fontSize: '20px' }">有遮罩</strong>
      <t-image
        src="https://tdesign.gtimg.com/demo/demo-image-1.png"
        :style="{ width: '284px', height: '160px' }"
        :overlay-content="renderMask"
      />
    </t-space>
    <t-space direction="vertical">
      <strong :style="{ fontSize: '20px' }">无遮罩</strong>
      <t-image
        src="https://tdesign.gtimg.com/demo/demo-image-1.png"
        :style="{ width: '284px', height: '160px' }"
        :overlay-content="renderButton"
      />
    </t-space>
  </t-space>
</template>

<script setup lang="jsx">
import { PrintIcon } from 'tdesign-icons-vue-next';
import { Tag } from 'tdesign-vue-next';

const renderMask = (
  <div
    style={{
      background: 'rgba(0,0,0,.4)',
      height: '100%',
      display: 'flex',
      alignItems: 'center',
      justifyContent: 'center',
      fontSize: '14px',
      lineHeight: '22px',
    }}
  >
    <Tag
      shape="mark"
      theme="warning"
      style={{
        borderRadius: '3px',
        background: 'transparent',
        color: '#fff',
      }}
    >
      <PrintIcon size="16" /> 高清
    </Tag>
  </div>
);

const renderButton = (
  <Tag
    shape="mark"
    theme="warning"
    style={{
      position: 'absolute',
      right: '8px',
      bottom: '8px',
      borderRadius: '3px',
      background: 'rgba(236,242,254,1)',
      color: 'rgba(0,82,217,1)',
    }}
  >
    <PrintIcon size="16" /> 高清
  </Tag>
);
</script>
