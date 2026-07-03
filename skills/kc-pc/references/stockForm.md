---
title: FormStyle 表单样式
lang: en-US
---

# FormStyle 表单样式
表单通用样式

## 基础用法
检索表单：
 `<el-form :inline="true" class="search-form"></el-form>`

```vue
<template>
  <el-form :inline="true" class="search-form">
        <el-form-item>
            <el-input v-model="searchForm.roleName" placeholder="角色名称" clearable></el-input>
        </el-form-item>
        <el-form-item>
            <el-select v-model="searchForm.roleCode" placeholder="角色编码">
                <el-option label="code1" value="1" />
                <el-option label="code2 two" value="2" />
            </el-select>
        </el-form-item>
        <el-form-item>
          <el-date-picker
            v-model="searchForm.daterange"
            type="daterange"
            align="right"
            unlink-panels
            range-separator="至"
            start-placeholder="申请开始日期"
            end-placeholder="申请结束日期"
            value-format="yyyy-MM-dd"
          />
        </el-form-item>
    </el-form>
</template>

<style lang="scss">

</style>
<script setup lang="ts">
import { onMounted, ref } from 'vue';
const searchForm = ref({roleName: '', roleCode: '', date: '', daterange: ''});
</script>

<style scoped lang="scss">
.search-form {
  .el-form-item{
    box-sizing: border-box;
    margin-right: 13px;
  }
  .el-select, .el-cascader, .el-autocomplete, .el-input,.select-wrapper
  {
    width: 185px;  
  }
  :deep(.el-date-editor--daterange, .el-date-editor--monthrange.el-input, .el-date-editor--monthrange.el-input__inner){
    width: 383px;
    height: 40px;
    line-height: 40px;
  }
  .search-form{
    font-size: 0;
  }.select-wrapper {
    display: inline-block;
  }
  :deep(.el-input--medium .el-input__inner ){
    height: 40px;
    line-height: 40px;
  }
  :deep(.el-input__wrapper){
    height: 40px;
    line-height: 40px;
  }
}
</style>
```

## API
|     参数    | 说明                                         | 类型           | 默认值           |
| ----------- | -------------------------------------------------------- | -------------- | -------------- |
| -- | -- | -- | -- |


