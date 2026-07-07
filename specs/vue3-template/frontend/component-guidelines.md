# 组件规范

> Vue3 组件开发规范。

---

## 概述

<!--

请分析项目组件开发规范，并补充：

- 组件组织方式
- 是否统一使用 `<script setup lang="ts">`
- Props、Emits、Slots 的使用方式
- UI 组件库、图标库、样式方案
- 推荐参考组件及历史遗留组件

-->

（由 AI 根据项目补充）

---

<!-- @trellis:protected:start -->
## **组件使用优先级**
AI 在开发时应遵循以下组件使用优先级：

1. 优先复用项目已有组件（如 `src/components`、`src/views/**/components`）。
2. 若不存在：
   - 移动端项目：读取 **kc-h5** Skill，优先使用团队 H5 组件。
   - PC 端项目：读取 **kc-pc** Skill，优先使用团队 PC 组件。
3. 若团队组件仍不存在：
   - 移动端优先使用 **Vant**。
   - PC 端优先使用 **Element Plus**。
4. 最后才允许新增公共组件。

禁止重复开发已有组件。
<!-- @trellis:protected:end -->
---

## 组件结构

<!--

分析项目组件的标准结构，例如：

- `<template>`
- `<script setup lang="ts">`
- `<style>`
- 代码组织顺序
- 生命周期组织方式

-->

（由 AI 根据项目补充）

---

## Props 规范

<!--

分析项目 Props、Emits、Slots 的使用规范，例如：

- Props 类型定义
- 默认值
- Emits 类型
- v-model 约定
- 插槽使用规范

-->

（由 AI 根据项目补充）

---

## 样式规范

<!--

分析项目样式方案，例如：

- CSS 预处理器
- Scoped
- CSS Modules
- UnoCSS / Tailwind
- 主题变量
- UI 组件库样式规范

-->

（由 AI 根据项目补充）

---


## 常见问题

<!--

结合项目代码，总结组件开发中的常见问题及注意事项。

-->

（由 AI 根据项目补充）
