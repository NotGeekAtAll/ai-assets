# 快速上手

## 介绍

通过本章节你可以了解到 `Kandy-h5` 的安装方法和基本使用姿势。

## 安装

可根据项目的包管理器进行安装，依赖[kandy-icon-h5](/h5/icon)

```bash
npm i @kc-one/kandy-h5 @kc-one/kandy-icon-h5
```

## 项目中使用

```typescript
import { createApp } from 'vue';
import kandyH5 from '@kc-one/kandy-h5';
import kandyIconH5 from '@kc-one/kandy-icon-h5';
import '@kc-one/kandy-h5/dist/style.css';

import App from './App.vue';

const app = createApp(App);

app.use(kandyH5);
app.use(kandyIconH5);
app.mount('#app');

```
