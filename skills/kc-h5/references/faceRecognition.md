---
aside: false
isShowMobile: true 
---

# FaceRecognition 人脸识别

## 基础用法
```vue
<template>
  <km-faceRecognition v-model:requestStatus="requestStatus" :request="request" />
</template>

<script lang="ts" setup>
import { ref } from 'vue';
const requestStatus = ref('');
const request = () => {
  setTimeout(function () {
    requestStatus.value = 'success';
  }, 3000);
};
</script>
```

## 插槽 Slots
```vue
<template>
  <km-faceRecognition v-model:requestStatus="requestStatus" :request="request" dom-ref="videoCaptureRef">
    <template #explain>
      自定义说明 slot
    </template>
  </km-faceRecognition>
</template>

<script lang="ts" setup>
import { ref } from 'vue';
const requestStatus = ref('');
const request = () => {
  setTimeout(function () {
    requestStatus.value = 'fail';
  }, 3000);
};
</script>
```
## API
|     参数    | 说明                                         | 类型           | 默认值           |
| ----------- | -------------------------------------------------------- | -------------- | -------------- |
| requestStatus | 接口请求状态 - 【必传】，可选值为 success fail  | string |  - |
| bgImage | 背景图片 | string |  - |
| domRef | dom ref，同页面多个输入框必传 | string |  - |

## Events
|     参数    | 说明      | 回调参数        |
| ----------- | ------------------------------- | -------------- |
| request | 接口请求方法 - 【必传】 | () => void |  - |





