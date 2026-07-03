---
---

# Icon 图标

## 说明
### 下载
```shell
npm i @kc-one/kandy-icon-pc
```
## 简单用法
```vue
<template>
   <kp-icon-crossFilled color="#6196cc" size="60"/>
</template>
```
```vue
<template>
   <kp-icon-add weight="bold"/><kp-icon-add/>

   <kp-icon-addition weight="bold"/><kp-icon-addition/>
</template>
```

## 图标合集
<IconListPc />

## API
|     参数    | 说明                                         | 类型           | 默认值            |
|------------ | --------------------------------------| -------------------------------- |----------------|
|         color		    |        svg 的 fill 颜色               |        string        | 继承颜色           |
|         class		    |        SVG 图标的大小, width x height               |       string      | 36  |
|         size		    |        SVG 图标的大小          |       number      | 36  |
|         weight【试用版】		    |        单色图标的线条粗细         |       string < 'normal' / 'bold' >     | normal |
