---
title: UploadImage 上传图片
---

# UploadImage 上传图片

单张图片上传组件

## 基础用法

```vue
<template>
  <kp-upload-image v-model="imgUrl" :upload-fn="uploadFn" />
</template>

<script lang="ts" setup>
import { UploadRequestOptions } from 'element-plus';
import { ref } from 'vue';

const imgUrl = ref('');

// 模拟上传文件
function uploadFn (options: UploadRequestOptions): Promise<{
  status: 'success' | 'fail';
  url: string
}> {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      const reader = new FileReader();
      // 获取上传的文件 options.file
      reader.readAsDataURL(options.file);
      reader.onload = () => resolve(
        // 返回status和url
        {
          status: 'success',
          url: reader.result as string,
        },
      );
      reader.onerror = reject;
    }, 1500);
  });
}

</script>
```

## 上传校验

```vue
<template>
  <kp-upload-image
    v-model="imgUrl" :upload-fn="uploadFn" :limit="2" accept="image/png,image/gif"
    accept-tip="请上传png、gif格式的图片"
  >
    <template #tips>
      <span>注：gif、png格式的图片；建议尺寸375*148px，大小不超过2M；</span>
    </template>
  </kp-upload-image>
</template>

<script lang="ts" setup>
import { UploadRequestOptions } from 'element-plus';
import { ref } from 'vue';

const imgUrl = ref('');

// 模拟上传文件
function uploadFn (options: UploadRequestOptions): Promise<{
  status: 'success' | 'fail';
  url: string
}> {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      const reader = new FileReader();
      // 获取上传的文件 options.file
      reader.readAsDataURL(options.file);
      reader.onload = () => resolve(
        // 返回status和url
        {
          status: 'success',
          url: reader.result as string,
        },
      );
      reader.onerror = reject;
    }, 1500);
  });
}
</script>

```

## 提示内容

```vue
<template>
  <kp-upload-image v-model="imgUrl" :upload-fn="uploadFn">
    <template #tips>
      <el-alert type="warning" :closable="false" style="padding: 0">
        注：仅支持jpg、jpeg、png格式的图片；建议尺寸375*148px，大小不超过2M；
      </el-alert>
    </template>
  </kp-upload-image>
</template>

<script lang="ts" setup>
import { UploadRequestOptions } from 'element-plus';
import { ref } from 'vue';

const imgUrl = ref('');

// 模拟上传文件
function uploadFn (options: UploadRequestOptions): Promise<{
  status: 'success' | 'fail';
  url: string
}> {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      const reader = new FileReader();
      // 获取上传的文件 options.file
      reader.readAsDataURL(options.file);
      reader.onload = () => resolve(
        // 返回status和url
        {
          status: 'success',
          url: reader.result as string,
        },
      );
      reader.onerror = reject;
    }, 1500);
  });
}
</script>

```

## 上传框的大小

```vue
<template>
  <kp-upload-image v-model="imgUrl" :upload-fn="uploadFn" width="200" height="140" />
</template>

<script lang="ts" setup>
import { UploadRequestOptions } from 'element-plus';
import { ref } from 'vue';

const imgUrl = ref('');

// 模拟上传文件
function uploadFn (options: UploadRequestOptions): Promise<{
  status: 'success' | 'fail';
  url: string
}> {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      const reader = new FileReader();
      // 获取上传的文件 options.file
      reader.readAsDataURL(options.file);
      reader.onload = () => resolve(
        // 返回status和url
        {
          status: 'success',
          url: reader.result as string,
        },
      );
      reader.onerror = reject;
    }, 1500);
  });
}

</script>
```

## 禁用上传
```vue
<template>
  <kp-upload-image v-model="imgUrl" :upload-fn="uploadFn" disabled />
  <p>el-form设置的disabled</p>
  <el-form disabled>
    <kp-upload-image v-model="imgUrl" :upload-fn="uploadFn" />
  </el-form>
</template>

<script lang="ts" setup>
import { UploadRequestOptions } from 'element-plus';
import { ref } from 'vue';

const imgUrl = ref('');

// 模拟上传文件
function uploadFn (options: UploadRequestOptions): Promise<{
  status: 'success' | 'fail';
  url: string
}> {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      const reader = new FileReader();
      // 获取上传的文件 options.file
      reader.readAsDataURL(options.file);
      reader.onload = () => resolve(
        // 返回status和url
        {
          status: 'success',
          url: reader.result as string,
        },
      );
      reader.onerror = reject;
    }, 1500);
  });
}

</script>
```

## API
### 属性
| 参数    | 说明                        | 类型                       | 默认值                            |
|-------|---------------------------|--------------------------|--------------------------------|
| width | 上传框宽度                     | string \| number         | 120                            |
| height | 上传框高度                     | string \| number         | 120                            |
| accept | 允许上传的文件类型，同input的accept属性 | string                   | image/jpeg,image/jpg,image/png |
| acceptTip | 类型错误时的提示文案                | string                   | 仅支持上传jpg、jpeg、png格式的图片!        |
| uploadText | 默认的上传文案                   | string                   | 上传图片                           |
| limit | 图片大小限制，单位为M               | number                   | 5                              |
|  disabled     | 禁用                        | boolean                  | false                          |
|        uploadFn       | 自定义的上传方法                  | Promise<UploadDataType\> | -                              |

### 类型
#### UploadDataType 上传方法返回类型
```typescript
export type UploadDataType = {
  status: 'success' | 'fail';
  url: string
}
```
