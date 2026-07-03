---
aside: false
isShowMobile: true 
---

# Sidebarkm 侧边导航

## 基础用法
```vue
<template>
  <km-sidebar :active="active" :list="list" />
</template>

<script lang="ts" setup>
import { ref } from 'vue';
const active = ref(1);
const list = ref(
  [
    { title: '产品要素' },
    { title: '准入要求' },
    { title: '禁入行业' },
    { title: '申请材料' },
  ],
);
</script>
```

## 禁用选项
```vue
<template>
  <km-sidebar :list="list" />
</template>

<script lang="ts" setup>
import { ref } from 'vue';
const list = ref(
  [
    { title: '产品要素' },
    { title: '准入要求', disabled: true },
    { title: '禁入行业' },
    { title: '申请材料' },
  ],
);
</script>
```

## 监听切换事件
```vue
<template>
  <km-sidebar :active="active" :list="list" :change="change" />
</template>

<script lang="ts" setup>
import { ref } from 'vue';
import { showToast } from 'vant';
const active = ref(2);
const list = ref(
  [
    { title: '产品要素' },
    { title: '准入要求' },
    { title: '禁入行业' },
    { title: '申请材料' },
  ],
);

const change = (index: number) => {
  showToast({ message: '索引：' + index });
};
</script>
```

## 徽标提示
```vue
<template>
  <km-sidebar :active="active" :list="list" />
</template>

<script lang="ts" setup>
import { ref } from 'vue';
const active = ref(2);
const list = ref(
  [
    { title: '产品要素', dot: true },
    { title: '准入要求', badge: 9 },

  ],
);
</script>
```

<!-- 
title	内容	string	''
dot	是否显示右上角小红点	boolean	false
badge	图标右上角徽标的内容	number | string	-
badge-props	自定义徽标的属性，传入的对象会被透传给 Badge 组件的 props	BadgeProps	-
disabled	是否禁用该项	boolean	false
url	点击后跳转的链接地址	string	-
to	点击后跳转的目标路由对象，等同于 Vue Router 的 to 属性	string | object	-
replace	是否在跳转时替换当前页面历史
 -->

## Sidebar API
|     参数    | 说明                                         | 类型           | 默认值           |
| ----------- | -------------------------------------------------------- | -------------- | -------------- |
| active | 当前导航项的索引 | number | string | 0 |
| list | 显示的内容列表 | [List API] | [] |


## Sidebar API
|     事件名    | 说明                                         | 回调参数           | 
| ----------- | -------------------------------------------------------- | -------------- | 
| change | 	切换导航项时触发 | 	index: number | 


## List API
|     参数    | 说明                                         | 类型           | 默认值           |
| ----------- | -------------------------------------------------------- | -------------- | -------------- |
| title | 内容 | string | '' |
| dot | 是否显示右上角小红点 | boolean | false |
| badge | 图标右上角徽标的内容 | number \| string | - |
| badge-props | 自定义徽标的属性，传入的对象会被透传给 Badge 组件的 props | BadgeProps | - |
| disabled | 是否禁用该项 | boolean | false |
| url | 点击后跳转的链接地址 | string | - |
| to | 点击后跳转的目标路由对象，等同于 Vue Router 的 to 属性 | string \| object | - |
| replace | 是否在跳转时替换当前页面历史 | boolean | false |


