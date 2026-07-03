---
title: AnchorScroll 锚点滚动菜单
lang: en-US
---

# AnchorScroll 锚点滚动菜单

基于Vue2.0开发的锚点滚动菜单。左边菜单栏，右边为滚动区域。左边的菜单栏和右边的滚动区域对应标题互相关联，可快速定位到对应的内容位置。

## 演示链接

- <http://dataloan.kingdee.com:89/#/product-addOrUpdateProduct>

## 基础用法

```html
<template>
<div class="scroll-layout">
  <AnchorScroll 
    :menuList="menuList" 
    titleClassName="anchor-item" 
    menuWidth="180px">
    <div class="main-content">
      <h2 class="anchor-item">菜单1</h2>
      <ul>
        <li v-for="i in 100" :key="1">菜单1{{i}}</li>
      </ul>
      <h2 class="anchor-item">菜单2</h2>
      <ul>
        <li v-for="i in 100" :key="1">菜单2{{i}}</li>
      </ul>
      <ul>
        <li v-for="i in 100" :key="1">菜单3{{i}}</li>
      </ul>
    </div>
  </AnchorScroll>
</div>
</template>
<script>
import AnchorScroll from '@/components/AnchorScroll/index.vue';
export default {
  name: 'AnchorScrollExample',
  components: {AnchorScroll},
  data() {
    return {
      menuList: ['菜单1', '菜单2', '菜单3', '菜单4']
    }
  }
}
</script>
<style scoped lang="scss">
.scroll-layout{ 
  // AnchorScroll 的父元素需要提供宽高，便于AnchorScroll组件确定宽高范围
  height: 100vh;
  width: 100vw;
}
</style>
```

## API

list-control-tp
|     参数    | 说明                                         | 类型           | 默认值           | 案例 |
| ----------- | --------------------------------- | -------------- | -------------- | -------------- |
| titleClassName | 对应标题的class名称 | String | 'scroll-title' | 'scroll-title'|
| menuWidth      | 菜单栏的宽度 | String|   '180px'    |     '260px'|
|menuList |菜单列表 |Array | [] | ['菜单1', '菜单2', '菜单3'] |

## 其它

已引用项目：

1. <https://git.kingdee.com/finance/wxservice-agent-web>
2. <https://git.kingdee.com/finance/wxservice-partner-web>
3. <https://git.kingdee.com/finance/finance-cloud-web>
4. <https://git.kingdee.com/finance/bizplat-ui>
