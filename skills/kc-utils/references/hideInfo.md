---
title: HideInfo 脱敏
lang: en-US
---

# HideInfo 脱敏
信息脱敏

## 手机号脱敏： hideMobile <kp-icon-verifyFilled color="#67c23a" size="30" style="display: inline-block; vertical-align: middle"/>
`隐藏中间四位号码`
```typescript
import { hideMobile } from '@kc-one/kandy-utils';
```
```vue
<template>
  <h3>手机号脱敏：</h3>
  <div>{{ hideMobile('13138888285') }}</div>
  <h3>固话脱敏：</h3>
  <div>{{ hideMobile('0756-12345678') }}</div>
  <div>{{ hideMobile('12355678') }}</div>
</template>
```

## 姓名脱敏： hideName <kp-icon-verifyFilled color="#67c23a" size="30" style="display: inline-block; vertical-align: middle"/>
`3个字内隐藏第1字` `4-6字隐藏前2字` `大于等于6个字隐藏3-6字`
```typescript
import { hideName } from '@kc-one/kandy-utils';
```
```vue
<template>
    <div>{{hideName('张三')}}</div>
    <div>{{hideName('李德峰')}}</div>
    <div>{{hideName('孤独求败')}}</div>
    <div>{{hideName('阿不都沙拉克')}}</div>
</template>
```

## 银行卡号脱敏： hideBankCard <kp-icon-verifyFilled color="#67c23a" size="30" style="display: inline-block; vertical-align: middle"/>
`保留前6位和后4位`
```typescript
import { hideBankCard } from '@kc-one/kandy-utils';
```
```vue
<template>
  <div>{{ hideBankCard('6236330017519800000') }}</div>
</template>
```

## 身份证脱敏： hideIdCard <kp-icon-verifyFilled color="#67c23a" size="30" style="display: inline-block; vertical-align: middle"/>
`隐藏后6位`
```typescript
import { hideIdCard } from '@kc-one/kandy-utils';
```
```vue
<template>
    <div>{{hideIdCard('513433200107100000')}}</div>
</template>
```

## 邮箱脱敏： hideEmail
`隐藏后6位`
```typescript
import { hideEmail } from '@kc-one/kandy-utils';
```
```vue
<template>
  <div>{{ hideEmail('112233@qq.com') }}</div>
  <div>{{ hideEmail('youxiang@126.com') }}</div>
</template>
```

## 企业名称脱敏： hideCorpName <kp-icon-verifyFilled color="#67c23a" size="30" style="display: inline-block; vertical-align: middle"/>
`隐藏4/5位`
```typescript
import { hideCorpName } from '@kc-one/kandy-utils';
```
```vue
<template>
    <div>{{hideCorpName('南京某某企业管理有限公司')}}</div>
    <div>{{hideCorpName('南京某某公司')}}</div>
</template>
```

## 统一信用社会代码脱敏： hideSocialCode <kp-icon-verifyFilled color="#67c23a" size="30" style="display: inline-block; vertical-align: middle"/>
`保留前4位和后4位`
```typescript
import { hideSocialCode } from '@kc-one/kandy-utils';
```
```vue
<template>
    <div>{{hideSocialCode('91450200MA5XXXXW06')}}</div>
</template>
```

## 地址脱敏： hideAddress <kp-icon-verifyFilled color="#67c23a" size="30" style="display: inline-block; vertical-align: middle"/>
`长度5个字一下保留前1位和后2位` `长度6-9字保留最后5位` `长度10以上，隐藏最后5个字之前的4位`

`严格模式：hideAddress(input, 'strict')`
```typescript
import { hideAddress } from '@kc-one/kandy-utils';
```
```vue
<template>
  <div>{{ hideAddress('浙江省杭州') }}</div>
  <div>{{ hideAddress('浙江省杭州市西湖区') }}</div>
  <div>{{ hideAddress('浙江省杭州市西湖区胡同口') }}</div>
  <h3>严格模式：</h3>
  <div>{{ hideAddress('浙江省杭州市西湖区胡同口', 'strict') }}</div>
</template>
```

## 任意字符串脱敏 stringDesensitise
`stringDesensitise(str:string, start:number, len:number)`

`start：开始索引位数` `len：隐藏位数`
```typescript
import { stringDesensitise } from '@kc-one/kandy-utils';
```
```vue
<template>
    <div>{{stringDesensitise('1234567890123456789', 2, 5)}}</div>
    <div>{{stringDesensitise('1234567890123456789', 0, 2)}}</div>
</template>
```



## 源码


## API
|     参数    | 说明                                         | 类型           | 默认值           |
| ----------- | -------------------------------------------------------- | -------------- | -------------- |
| input | 需要脱敏的字符串 | string | -- |


