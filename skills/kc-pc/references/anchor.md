---
title: Anchor 锚点
lang: en-US
---

# Anchor 锚点
用于后台管理系统表单过长，分组并定位到对应位置，减少用户滑动，提高用户体验。

## 基础用法

```vue
<template>
  <div class="my-container">
    <div class="left-area">
      <kp-anchor :items="items" scroll-container=".right-area" />
    </div>
    <div class="right-area">
      <div id="baseInfo" class="section-wrapper" style="background-color: lightblue">
        <div>基本信息</div>
      </div>
      <div id="pushInfo" class="section-wrapper" style="background-color: lightcyan">
        <div>数据推送</div>
      </div>
      <div id="loanInfo" class="section-wrapper" style="background-color: lightsalmon">
        <div>贷款信息</div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">

import { onMounted, ref } from 'vue';

const items = ref<any[]>([]);

onMounted(() => {
  setTimeout(() => {
    items.value = [
      {
        title: '基本信息',
        id: 'baseInfo',
      },
      {
        title: '数据推送',
        id: 'pushInfo',
      },
      {
        title: '贷款信息',
        id: 'loanInfo',
      },
    ];
  }, 1000);
});
</script>
<style lang="scss">
.my-container {
  display: flex;
  height: 200px;

  .left-area {
    width: 200px;
    border-right: 1px solid #f1f1f1;
  }
}

.right-area {
  flex: 1;
  overflow: auto;

  .section-wrapper {
    padding: 16px;
    height: 300px;
    border-bottom: 1px solid #eee;
  }
}
</style>
```

## API
|     参数    | 说明     | 类型                              | 默认值    |
| ----------- |--------|---------------------------------|--------|
| items | tab的内容 | Arrary\<AnchorItem\>            | []     |
| scroll-container | 滚动的元素  | string \| HTMLElement \| Window | window |


