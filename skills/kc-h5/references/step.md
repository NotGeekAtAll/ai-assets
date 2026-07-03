---
aside: false
isShowMobile: true 
---

# Step 进度条

## 一般用法
```vue
<template>
  <km-step :current="currentStep" :step-list="steps" />
  <km-button class="!mt-40" @click="handleClickNext">
    下一步
  </km-button>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import { KmStepItem } from 'kc-one-ui';

const currentStep = ref(1);

const steps: KmStepItem[] = [
  {
    key: 1,
    label: '身份信息',
  },
  {
    key: 2,
    label: '信息补充',
  },
  {
    key: 3,
    label: '申贷信息',
  },
];

function handleClickNext () {
  if (currentStep.value === 3) {
    currentStep.value = 1;
  } else {
    currentStep.value += 1;
  }
}
</script>

<style lang="scss">

</style>
```

## API
| 参数       | 说明   | 类型     | 默认值 |
|----------|------|--------|-----|
| current  | 当前步骤 | number | 1   |
| stepList | 步骤列表 | array  | []  |

### 类型
```typescript

export type KmStepItem = {
  key: number;
  label: string;
};

export type KmStepProps = {
  stepList: KmStepItem[];
  current: number;
};
```
