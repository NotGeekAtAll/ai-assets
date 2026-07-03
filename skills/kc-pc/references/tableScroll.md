---
title: TableScroll 双滚动条表格
lang: en-US
---

# TableScroll 双滚动条表格

上下双滚动条表格

## 基础用法

在需要的页面中直接引用, 用法和`element-plus`中的`table`组件一样。

不同的是，这里增加了上下双滚动条。

且值得注意的是，为了让滚动条更加明显，el-table组件属性中的`scrollbar-always-on`属性，当前组件设置默认值为`true`。可以在使用时加上：`:scrollbar-always-on="false"`进行覆盖
```vue
<script lang="ts" setup>
const data = [
  { name: 'xiaowang', age: '19', address: 'No. 189, Grove St, Los Angeles' },
  { name: 'xiaowang2', age: '20', address: 'No. 189, Grove St, Los Angeles' },
  { name: 'xiaowang3', age: '20', address: 'No. 189, Grove St, Los Angeles' },
];
const rowClick = (row:any) => {
  console.log(row, '======');
};
</script>

<template>
  <h3>无滚动条的效果</h3>
  <kp-table-scroll class="vp-raw" border :data="data" @row-click="rowClick">
    <el-table-column label="姓名" prop="name" width="200px" />
    <el-table-column label="年龄" prop="age" />
  </kp-table-scroll>
  <h3>有滚动条的效果</h3>
  <kp-table-scroll class="vp-raw" border :data="data">
    <el-table-column label="姓名" prop="name" width="200px" />
    <el-table-column label="年龄" prop="age" width="200px" />
    <el-table-column label="地址" prop="address" width="600px" />
  </kp-table-scroll>
  <h3>ElTable原来的滚动效果</h3>
  <el-table class="vp-raw" border :data="data" scrollbar-always-on>
    <el-table-column label="姓名" prop="name" width="200px" />
    <el-table-column label="年龄" prop="age" width="200px" />
    <el-table-column label="地址" prop="address" width="600px" />
  </el-table>
</template>

<style scoped lang="scss">
</style>
```

## API

请参考：[Element Plus Table](https://element-plus.gitee.io/zh-CN/component/table.html)
