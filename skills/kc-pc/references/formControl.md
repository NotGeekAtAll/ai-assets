---
title: FormControl 动态表单
lang: en-US
---

# FormControl 动态表单
通用描述


## 演示链接   
- http://dataloan.kingdee.com:89/#/order-order

## 基础用法

```shell
npm i @kc-one/kandy-icon-pc

import ColumnControlTp from '@/components/ColumnControl/columnTp.vue';  // 动态列组件
import ColumnControlPopup from '@/components/ColumnControl/popup.vue';  // 动态控制组件

// 加密电话号码、企业名称
import EncryptMobile from '@/components/ColumnControl/common/encryptMobile.vue';
import EncryptCompanyName from '@/components/ColumnControl/common/encryptCompanyName.vue';

 // 动态列
<column-control-tp :columnList="columnList" columnWidthLg="companyName">
    // 自定义钩子 - slot传columnList返回field
    <template slot="`header-${item.field}`" slot-scope="scope">
        自定义表头内容
    </template>
    <template slot="item.field" slot-scope="scope">
        自定义内容
        <encrypt-mobile :fieldValue="scope.row.mobile"></encrypt-mobile>
    </template>
</column-control-tp>

// 更新列表
// table添加ref="trendTable"
<el-table ref="trendTable"> </el-table>


// js 获取动态列表头 后 执行this.$refs.trendTable.doLayout();
const getFieldConfig = () => {
    this.columnList = [];
    this.$http({
    url: this.$http.adornUrl('/field/config/query'),
    method: 'post',
    data: {
        dataType: this.columnDataType
    }
    }).then(({ data }) => {
    if (data && data.code === 200) {
        this.columnList = data.data && data.data.fields;
        this.$nextTick(() => {
        this.$refs.trendTable.doLayout();
        })
    } else {
        this.$message({ type: 'error', message: data.msg });
    }
    });
}
```

## API
list-control-tp
|     参数    | 说明                                         | 类型           | 默认值           | 案例 | 
| ----------- | ----------------------------- | -------------- | -------------- | -------------- |
| columnList | 列数组 | Array | [ ] | '[{field:‘列英文名’, fieldName:‘列中文名’, id:‘列id’, orderNum:‘排序’, visible:‘是否显示’ }]'|
|width|列宽度|String|Number|120|
|columnWidthLg	|列宽度为150px-传columnList返回field值	|string|	‘’	|columnWidthLg=“companyName, mobile”|
|columnWidthSm	|列宽度为90px-传columnList返回field值	|string|	‘’	|columnWidthLg=“companyName, mobile”|
|# template	|自定义钩子-slot传columnList返回field 值	|DOM|	-	|template slot=“mobile” slot-scope=“scope”|



list-control-popup
|     参数    | 说明                                         | 类型           | 默认值           | 案例 | 
| ----------- | ----------------------------- | -------------- | -------------- | -------------- |
|callBack	|成功回调	|Function	|() => {}	|getFieldConfig|
|dataType	|获取表头列传参	|String	|’ ’	|‘BizOrderOldDTO’ - 订单表头列参数|