---
aside: false
isShowMobile: true
---

# DefaultPage 缺省页

## 基础用法

```vue
<template>
  <van-tabs v-model:active="active">
    <van-tab v-for="type in typeNameArr" :key="type" :title="type">
      <km-default-page :type="type" />  <!-- 暂无网络 -->
    </van-tab>
  </van-tabs>
</template>

<script lang="ts" setup>
import { DefaultPageType, defaultPageTypeMap } from 'kc-one-ui';
import { ref } from 'vue';

const active = ref(0);

const typeNameArr = Object.keys(defaultPageTypeMap) as DefaultPageType[];

</script>
```

## 自定义

```vue
<template>
  <!--  自定义图标 -->
  <km-default-page description="自定义图标" image-size="small" km-icon="km-icon-accountOther" />

  <!--  自定义文案 / 换行 -->
  <km-default-page type="network" description="自定义文案 / 换行" />

  <!--  自定义图片大小 -->
  <km-default-page km-icon="km-icon-bankcardOther" description="自定义图片大小" image-size="mini" />

  <!--  自定义图片 -->
  <km-default-page
    description="自定义图片"
    image-url="https://loan.kdbank.cn/file/group1/M00/00/13/oYYBAGOTH6qAeBjVAAFkFT6pEbg771.png"
  />
</template>
```

## Slot

```vue
<template>
  <km-default-page>
    <km-icon-resultSuccessOther size="56" />
    <p>自定义内容</p>
  </km-default-page>
</template>
```

## API

| 参数          | 说明                                                                                     | 类型     | 默认值     |
|-------------|----------------------------------------------------------------------------------------|--------|---------|
| type        | 类型，可选值为 network、news、page、inviteRecord、coupon、customer、inquireRecord、product、team、wait | string | default |
| image-url   | 自定义图片链接                                                                                | string | -       |
| image-size  | 图片大小， 可选值为 normal、large、small、mini                                                     | string | normal  |
| description | 自定义文案                                                                                  | string | -       |
