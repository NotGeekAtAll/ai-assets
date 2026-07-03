---
aside: false
isShowMobile: true 
---

# Dialog 弹窗

## 基础用法 - 圆角按钮
```vue
<template>
  <km-button :text="true" plain @click="show=true">
    默认弹窗
  </km-button>
  <km-dialog v-model:show="show" :content="content" :confirm="confirm" />

  <p class="mt-10" />
  <km-button :text="true" plain @click="plainShow=true">
    朴素按钮弹窗
  </km-button>
  <km-dialog
    v-model:show="plainShow" :content="content" :show-plain-button="true"
    :show-cancel-button="false" :confirm="confirm" :plain-confirm="plainConfirm"
  />
</template>

<script lang="ts" setup>
import { ref } from 'vue';
const show = ref(false);
const plainShow = ref(false);
const content = ref('该企业在本产品下已有流程中的订单，\n 是否继续申请？');
const confirm = () => {
  setTimeout(() => {
    show.value = false;
    plainShow.value = false;
  }, 2000);
};
const plainConfirm = () => {
  plainShow.value = false;
};
</script>
```

## 竖排按钮
```vue
<template>
  <km-button :text="true" plain @click="show=true">
    竖排按钮弹窗
  </km-button>
  <km-dialog v-model:show="show" :content="content" :confirm="confirm" button-position="V" />

  <p class="mt-10" />
  <km-button :text="true" plain @click="VShow=true">
    朴素竖排按钮弹窗
  </km-button>
  <km-dialog
    v-model:show="VShow" :content="content" button-position="V" :show-plain-button="true"
    :confirm="confirm" :plain-confirm="() => VShow = false"
  />
</template>

<script lang="ts" setup>
import { ref } from 'vue';
const show = ref(false);
const VShow = ref(false);
const content = ref('该企业在本产品下已有流程中的订单，\n 是否继续申请？');
const confirm = () => {
  show.value = false;
  VShow.value = false;
};
</script>
```

## 弱化按钮
```vue
<template>
  <km-button :text="true" plain class="pt-20" @click="show=true">
    点击预览
  </km-button>
  <km-dialog v-model:show="show" :content="content" :button-reduction="true" @click="confirm" />
</template>

<script lang="ts" setup>
import { ref } from 'vue';
const show = ref(false);
const content = ref('该企业在本产品下已有流程中的订单，\n 是否继续申请？');
const confirm = () => {
  show.value = false;
};
</script>
```

## 内容自定义卡槽
```vue
<template>
  <km-button :text="true" plain class="pt-20" @click="show = true">
    点击预览
  </km-button>
  <km-dialog v-model:show="show" :close-on-click-overlay="true" content="123" @click="confirm">
    <template #default>
      <km-icon-rechargeOther />
      <p>内容太长了，显示滚动条。 内容太长了，显示滚动条。 内容太长了，显示滚动条。 内容太长了，显示滚动条。 内容太长了，显示滚动条。 内容太长了，显示滚动条。 内容太长了，显示滚动条。 内容太长了，显示滚动条。 内容太长了，显示滚动条。 内容太长了，显示滚动条。 内容太长了，显示滚动条。 内容太长了，显示滚动条。 内容太长了，显示滚动条。 内容太长了，显示滚动条。 内容太长了，显示滚动条。 内容太长了，显示滚动条。 内容太长了，显示滚动条。 内容太长了，显示滚动条。 内容太长了，显示滚动条。 内容太长了，显示滚动条。 内容太长了，显示滚动条。 内容太长了，显示滚动条。 内容太长了，显示滚动条。 内容太长了，显示滚动条。 </p>
    </template>

    <template #footer>
      <km-button @click="show = false">
        取消
      </km-button>
    </template>
  </km-dialog>
</template>

<script lang="ts" setup>
import { ref } from 'vue';
const show = ref(false);
const confirm = () => {
  show.value = false;
};
</script>
```

## API
|     参数    | 说明                                         | 类型           | 默认值           |
| ----------- | -------------------------------------------------------- | -------------- | -------------- |
| show | 是否显示 - 【必传】 | boolean | false |
| title | 主标题 | string | 温馨提示 |
| content | 文本内容，支持通过 \n 换行 | string | - |
| confirmButtonText | 确定按钮文案 | string | 确认 |
| showConfirmButton | 是否显示确定按钮 | boolean | true |
| cancelButtonText | 取消按钮文案 | string | 取消 |
| showCancelButton | 是否显示取消按钮 | boolean | true |
| plainButtonText | 朴素按钮文案 | string | - |
| showPlainButton | 是否显示朴素按钮 | boolean | false |
| buttonReduction | 是否为弱化按钮 | boolean | false |
| buttonPosition | H水平 V垂直 | string | H |
| closeOnClickModal | 是否点击遮罩关闭弹窗 | boolean | false |



## Events
|     参数    | 说明      | 回调参数        |
| ----------- | ------------------------------- | -------------- |
| close | 关闭回调 - 【必传】 | () => void |
| confirm | 确认回调  | () => void |
| plainConfirm | 朴素按钮回调 | () => void |
| cancel | 取消回调 | () => void |


## Slots
|     参数    | 说明      | 
| ----------- | ------------------------------- |
| default | 自定义内容 |
| footer  | 自定义底部按钮区域 |


