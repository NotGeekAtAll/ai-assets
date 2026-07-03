---
title: NumberFormat 数字格式化
lang: en-US
---

# NumberFormat 数字格式化
数字格式化处理

## 格式化金额
`每3位加 “,” 号 `
```typescript
import { formatPrice } from '@kc-one/kandy-utils';
```
```vue
<template>
    <div>{{formatPrice('100005333.00')}}</div>
    <div>{{formatPrice('100005333.55')}}</div>
</template>
```

## API
|     参数    | 说明                                         | 类型           | 默认值           |
| ----------- | -------------------------------------------------------- | -------------- | -------------- |
| -- | -- | -- | -- |


