---
aside: false
isShowMobile: true
---

# Button 按钮

## 主按钮
```vue
<template>
  <km-button type="primary" disabled>
    不可点
  </km-button>
  <km-button type="primary">
    常态
  </km-button>
  <km-button type="primary">
    按下
  </km-button>
  <km-button type="primary" loading>
    加载中
  </km-button>
</template>

<style lang="scss">
.h5-phone-container {
  .km-button + .km-button {
    margin-top: 20px;
  }
}
</style>
```

## 幽灵按钮
```vue
<template>
  <km-button plain disabled>
    不可点
  </km-button>
  <km-button plain>
    常态
  </km-button>
  <km-button plain type="success">
    按下
  </km-button>
  <km-button plain loading loading-text="加载中" />
</template>
```

## 次要幽灵按钮
```vue
<template>
  <km-button disabled>
    不可点
  </km-button>
  <km-button>常态</km-button>
  <km-button type="success">
    按下
  </km-button>
  <km-button loading>
    加载中
  </km-button>
</template>
```

## API
|     参数    | 说明                                         | 类型           | 默认值           |
| ----------- | -------------------------------------------------------- | -------------- | -------------- |
| type        | 类型，可选值为 primary success warning danger  |     string     | default           |
| disabled    | 是否禁用按钮  |     boolean     | false           |
| plain    | 是否为朴素按钮  |     boolean     | false           |
| loading    | 是否显示为加载状态  |     boolean     | false           |
| loading-text    | 	加载状态提示文字  |     string     | -           |
