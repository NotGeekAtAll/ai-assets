---
aside: false
isShowMobile: true 
---

# Cell 单元格

## 基础用法
```vue
<template>
  <km-cell title="单元格" value="内容" />
  <km-cell title="单元格" is-link @click="fnClick" />
  <km-cell title="单元格" is-link value="内容" :click="fnClick" />
</template>

<script lang="ts" setup>
import { showToast } from 'vant';
const fnClick = () => {
  showToast({ message: '点击回调' });
};
</script>
```

## 展示图标
```vue
<template>
  <km-cell title="展示图标" icon="location-o" is-link />
  <km-cell title="展示图标" icon="km-icon-detailOther" is-link />
  <km-cell title="展示图标" icon="https://loan.kdbank.cn/finPartner/img/code-bglogo.aa9fa0e5.png" is-link />
</template>
```

## 页面导航
```vue
<template>
  <km-cell title="链接跳转" url="https://www.baidu.com/" is-link />
  <km-cell title="点击回调" :click="clickFn" is-link />
  <km-cell title="路由跳转" to="/h5/defaultPage" is-link />
</template>

<script lang="ts" setup>
import { showToast } from 'vant';
const clickFn = () => {
  console.log('点击回调');
  showToast({ message: '点击回调' });
};
</script>
```

## 使用插槽
```vue
<template>
  <km-cell is-link>
    <template #title>
      使用插槽
      <span class="text-[#ABABAB] text-13 ml-10">
        备注
      </span>
    </template>
  </km-cell>
  <km-cell title="使用插槽" is-link>
    <template #rightIcon>
      <km-icon-rightFilled class="text-[#ABABAB] w-15 h-15" />
    </template>
  </km-cell>
  <km-cell title="使用插槽" is-link>
    <template #extra>
      <span class="text-[#ABABAB] text-13 ml-10">
        备注
      </span>
    </template>
  </km-cell>
</template>
```

## Sidebar Props
|     参数    | 说明                                         | 类型           | 默认值           |
| ----------- | -------------------------------------------------------- | -------------- | -------------- |
| -- | -- | -- | -- |
| title | 左侧标题 | number \| string | - |
| value | 右侧内容 | number \| string | - |
| url | 点击后跳转的链接地址 | string | - |
| to | 点击后跳转的目标路由对象，等同于 Vue Router 的 to 属性 | string \| object | - |
| replace | 是否在跳转时替换当前页面历史 | boolean | false |
| is-link | 是否展示右侧箭头并开启点击反馈 | boolean | false |


## Sidebar Events
|     事件名    | 说明                                         | 回调参数           | 
| ----------- | -------------------------------------------------------- | -------------- | 
| click | 	点击单元格时触发 | 	EventHandle | 



## Sidebar Slots
|     名称    | 说明                                         |
| ----------- | -------------------------------------------------------- | 
| title | 	自定义左侧标题 | 
| value | 	自定义右侧内容 | 
| label | 	自定义标题下方的描述信息 | 
| icon | 	自定义左侧图标 | 
| right-icon | 	自定义右侧图标 | 
| extra | 	自定义单元格最右侧的额外内容 |
