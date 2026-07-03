---
title: Regular 正则校验
lang: en-US
---

# Regular 正则校验


## 手机号校验： isMobileReg
`11位数字` `1开头`
```bash
import { isMobileReg } from '@kc-one/kandy-utils';
```
```vue
<template>
    <div>isMobileReg("18381885855"); <span style="color: #9191ad">// {{isMobileReg('18381885855')}}</span></div>
    <div>isMobileReg("1838188585g"); <span style="color: #9191ad">// {{isMobileReg('1838188585')}}</span></div>
</template>

<script>
// 正则表达式
const reg = /^1[0-9]{10}$/;
</script>


```

## 验证码校验： isSmsCodeReg
`6位数字` 
```bash
import { isSmsCodeReg } from '@kc-one/kandy-utils';
```
```vue
<template>
    <div>isSmsCodeReg("123456"); <span style="color: #9191ad">// {{isSmsCodeReg('123456')}}</span></div>
    <div>isSmsCodeReg("12345g"); <span style="color: #9191ad">// {{isSmsCodeReg('12345g')}}</span></div>
</template>

<script>
// 正则表达式
const reg = /\d{6}/;
</script>


```

## 统一社会信用代码 isSocialCodeReg
`18位数字或大写英文字母` 
```bash
import { isSocialCodeReg } from '@kc-one/kandy-utils';
```
```vue
<template>
    <div>isSocialCodeReg("91450200MA5NKP7W06"); <span style="color: #9191ad">// {{isSocialCodeReg('91450200MA5NKP7W06')}}</span></div>
    <div>isSocialCodeReg("91450200MA5NKP7W0"); <span style="color: #9191ad">// {{isSocialCodeReg('91450200MA5NKP7W0')}}</span></div>
</template>

<script>
// 正则表达式
const reg = /^([0-9A-HJ-NPQRTUWXY]{2}\d{6}[0-9A-HJ-NPQRTUWXY]{10}|[1-9]\d{14})$/;
</script>


```

## 密码校验： isPasswordReg <kp-icon-verifyFilled color="#67c23a" size="30" style="display: inline-block; vertical-align: middle"/>
`8-20位`  `至少包括1个大写字母，1个小写字母，1个数字，1个特殊字符` 
```bash
import { isPasswordReg } from '@kc-one/kandy-utils';
```
```vue
<template>
    <div>isPasswordReg("AbcDEFF123$"); <span style="color: #9191ad">// {{isPasswordReg('AbcDEFF123,')}}</span></div>
    <div>isPasswordReg("AbcDEFF1234"); <span style="color: #9191ad">// {{isPasswordReg('AbcDEFF123')}}</span></div>
</template>

<script>
// 正则表达式
const reg = /^(?=.*[A-Z])(?=.*[a-z])(?=.*\d)(?=.*[$@$!%*#`~^&*()_+<>:"{},./;?&])[A-Za-z\d$@$!%*#`~!^&*()_+<>:"{},./;?&]{8,20}$/;
</script>


```

## 身份证号校验： isIdCardReg
` 15位或18位` `地址编码、出生日期和校验位的验证` `最后一位允许X`
```bash
import { isIdCardReg } from '@kc-one/kandy-utils';
```
```vue
<template>
    <div>isIdCardReg("51343319980101212X"); <span style="color: #9191ad">// {{isIdCardReg('51343319980101212X')}}</span></div>
    <div>isIdCardReg("51343319982101212X"); <span style="color: #9191ad">// {{isIdCardReg('51343319982101212X')}}</span></div>
</template>

<script>
// 正则表达式
const reg = /^\d{6}(19|2\d)?\d{2}(0[1-9]|1[012])(0[1-9]|[12]\d|3[01])\d{3}(\d|X)?$/;
</script>


```

## 港澳居民往来大陆通行证： isGAIdCardReg
`长度必须为9位或11位` `第一位为字母H或M` `后8位或10位必须为数字`
```bash
import { isGAIdCardReg } from '@kc-one/kandy-utils';
```
```vue
<template>
    <div>isGAIdCardReg("H12345678"); <span style="color: #9191ad">// {{isGAIdCardReg('H12345678')}}</span></div>
    <div>isGAIdCardReg("A12345678"); <span style="color: #9191ad">// {{isGAIdCardReg('A12345678')}}</span></div>
</template>

<script>
    // 正则表达式
    const reg = /^[HMhm]{1}([0-9]{10}|[0-9]{8})$/;
</script>


```

## 台湾居民往来大陆通行证： isTWIdCardReg
` 长度必须为8位或10-18位`    ` 位证件必须为 8 位数字`
```bash
import { isTWIdCardReg } from '@kc-one/kandy-utils';
```
```vue
<template>
    <div>isTWIdCardReg("123456789012345678"); <span style="color: #9191ad">// {{isTWIdCardReg('123456789012345678')}}</span></div>
    <div>isTWIdCardReg("12345678"); <span style="color: #9191ad">// {{isTWIdCardReg('12345678')}}</span></div>
</template>

<script>
    // 正则表达式
    const reg = /^\d{8}$|^[a-zA-Z0-9]{10}$|^\d{18}$/;
</script>


```


## 银行卡号校验： isBankCardReg
`12-20位数字`
```bash
import { isBankCardReg } from '@kc-one/kandy-utils';
```
```vue
<template>
    <div>isBankCardReg("12345678901234567890"); <span style="color: #9191ad">// {{isBankCardReg('12345678901234567890')}}</span></div>
    <div>isBankCardReg("123456789012345678901"); <span style="color: #9191ad">// {{isBankCardReg('123456789012345678901')}}</span></div>
</template>

<script>
// 正则表达式
const reg = /^\d{12,20}$/;
</script>


```

## 邮箱校验： isEmailReg
`匹配@符号` `@后，允许大小写字母、数字以及"-"的出现` `.后必须是字母` 
```bash
import { isEmailReg } from '@kc-one/kandy-utils';
```
```vue
<template>
    <div>isEmailReg("11111@qq.com"); <span style="color: #9191ad">// {{isEmailReg('11111@qq.com')}}</span></div>
    <div>isEmailReg("111111qq.com"); <span style="color: #9191ad">// {{isEmailReg('111111qq.com')}}</span></div>
</template>

<script>
// 正则表达式
const reg = /^([a-zA-Z0-9_-])+@([a-zA-Z0-9_-])+((.[a-zA-Z0-9_-]{2,3}){1,2})$/;
</script>


```

## URL地址校验： isURLReg
`匹配http或https` `匹配:和//`
```bash
import { isURLReg } from '@kc-one/kandy-utils';
```
```vue
<template>
    <div>isURLReg("https://loan.kdbank.cn/kandy-ui"); <span style="color: #9191ad">// {{isURLReg('https://loan.kdbank.cn/kandy-ui')}}</span></div>
    <div>isURLReg("htt://loan.kdbank.cn/kandy-ui"); <span style="color: #9191ad">// {{isURLReg('htt://loan.kdbank.cn/kandy-ui')}}</span></div>
</template>

<script>
// 正则表达式
const reg = /^http[s]?:\/\/.*/;
</script>


```

## 两位小数校验： is2DecimalReg
```bash
import { is2DecimalReg } from '@kc-one/kandy-utils';
```
```vue
<template>
    <div>is2DecimalReg("20.22"); <span style="color: #9191ad">// {{is2DecimalReg('20.22')}}</span></div>
    <div>is2DecimalReg("20.223"); <span style="color: #9191ad">// {{is2DecimalReg('20.223')}}</span></div>
</template>

<script>
// 正则表达式
const reg = /(^[1-9]\d*(\.\d{1,2})?$)|(^0(\.\d{1,2})?$)/;
</script>


```

## API
|     参数    | 说明                                         | 类型           | 默认值           |
| ----------- | -------------------------------------------------------- | -------------- | -------------- |
| input | 必传-需要校验的字符串 | string | -- |

returns isValidate boolean 必须返回 校验的结果 true 通过 false 不通过

