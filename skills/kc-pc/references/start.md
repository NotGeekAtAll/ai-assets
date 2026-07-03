# 快速上手

## 介绍

通过本章节你可以了解到 `Kandy-pc` 的安装方法和基本使用姿势。

## 安装

可根据项目的包管理器进行安装，依赖[kandy-icon-pc](/pc/icon)

```bash
npm i @kc-one/kandy-pc @kc-one/kandy-icon-pc
```

## 项目中使用

```typescript
import { createApp } from 'vue';
import kandyPc from '@kc-one/kandy-pc';
import kandyIconPc from '@kc-one/kandy-icon-pc';
import '@kc-one/kandy-pc/dist/style.css';

import App from './App.vue';

const app = createApp(App);

app.use(kandyPc);
app.use(kandyIconPc);
app.mount('#app');

```
