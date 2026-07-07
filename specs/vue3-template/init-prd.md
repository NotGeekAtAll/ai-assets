# Bootstrap 任务：完善项目开发规范

**你（AI）正在执行此任务，开发者不会阅读此文件。**

开发者刚刚在这个项目中第一次执行了 `trellis init`。
现在 `.trellis/` 已创建，并包含空的规范（spec）脚手架，同时该 Bootstrap 任务也位于 `.trellis/tasks/` 下。当开发者准备处理此任务时，应在支持 Trellis Session Identity 的 AI 会话中启动它。

**你的任务**：帮助开发者完善 `.trellis/spec/` 中的团队开发规范。

之后每一次 AI 会话中，`trellis-implement` 与 `trellis-check` 子代理都会自动加载当前任务 `jsonl` 清单中指定的 spec 文件。

**如果 spec 是空的，子代理只能生成通用风格的代码；如果 spec 足够完善，它们就会按照团队的实际编码规范工作。**

不要直接输出一大堆说明。请先简单打个招呼，询问项目中是否已有规范文档（如 `CLAUDE.md`、`.cursorrules` 等），然后以对话方式逐步完成整个过程。

---

## 当前进度（完成后请更新勾选状态）

- [ ] 完善前端开发规范
- [ ] 添加真实代码示例

---

## 需要完善的 Spec 文件

**注意：<!-- @trellis:immutable:start --> 和 <!-- @trellis:immutable:end -->之间的内容不可修改，完全保持原有内容**

### 前端开发规范

| 文件 | 需要记录的内容 |
|------|----------------|
| `.trellis/spec/frontend/directory-structure.md` | 页面、组件、Hook 等目录组织方式 |
| `.trellis/spec/frontend/component-guidelines.md` | 组件开发模式、Props 等约定 |
| `.trellis/spec/frontend/hook-guidelines.md` | 自定义 Hook 命名与使用模式 |
| `.trellis/spec/frontend/state-management.md` | 状态管理方案、数据放置位置 |
| `.trellis/spec/frontend/coding-style.md` | 代码规范 |
| `.trellis/spec/frontend/api-guidelines.md` | api 调用 |
| `.trellis/spec/frontend/router-guidelines.md` | 路由 |
| `.trellis/spec/frontend/utils-guidelines.md` | 工具库utils |

### Thinking Guides（已预填充）

`.trellis/spec/guides/` 中已经包含通用的 Thinking Guides（思考指南）。

**只有当其中内容明显不适用于当前项目时，才需要进行调整。**

---

## 如何完善 Spec

### 第一步：优先导入已有规范（推荐）

先扫描项目中已有的规范文档。

如果存在，请读取内容，并提取其中的规则填充到对应的 `.trellis/spec/` 文件中。

相比重新编写，这通常速度更快，也更符合项目实际情况。

| 文件 / 目录 | 对应工具 |
|------|------|
| `CLAUDE.md` / `CLAUDE.local.md` | Claude Code |
| `AGENTS.md` | Codex / Claude Code / 兼容 Agent 的工具 |
| `.cursorrules` | Cursor |
| `.cursor/rules/*.mdc` | Cursor Rules |
| `.windsurfrules` | Windsurf |
| `.clinerules` | Cline |
| `.roomodes` | Roo Code |
| `.github/copilot-instructions.md` | GitHub Copilot |
| `.vscode/settings.json` → `github.copilot.chat.codeGeneration.instructions` | VS Code Copilot |
| `CONVENTIONS.md` / `.aider.conf.yml` | aider |
| `CONTRIBUTING.md` | 通用项目规范 |
| `.editorconfig` | 编辑器格式规范 |

---

### 第二步：分析代码库，补充文档中未覆盖的内容

扫描真实代码，找出实际使用的开发模式。

在编写每一个 Spec 文件之前，都应：

- 找到 **2~3 个真实代码示例**
- 引用真实文件路径（不要写假路径）
- 总结团队明确避免使用的反模式（Anti-pattern）

---

### 第三步：记录现实，而不是理想

**非常重要：记录项目当前真实采用的方式，而不是你认为应该采用的最佳实践。**

由于 Trellis 子代理会严格按照 Spec 编写代码：

如果 Spec 中写的是项目实际上没有采用的模式，AI 后续生成的代码就会与整个项目风格不一致。

即使项目存在技术债务，也应该记录当前真实状态。

优化方案应该留到后续讨论，而不是在 Bootstrap 阶段修改 Spec。

---

## Runtime 工作原理（当开发者问“为什么需要 Spec？”时再说明）

可以向开发者解释：

- 每个 AI 编码任务都会启动两个子代理：
  - `trellis-implement`：负责编写代码
  - `trellis-check`：负责检查代码质量
- 每个任务都包含：
  - `implement.jsonl`
  - `check.jsonl`
- 这些文件指定了需要加载哪些 Spec。
- 平台 Hook 会自动将：
  - 当前任务的 `prd.md`
  - 对应的 `.trellis/spec/`
  注入到两个子代理的 Prompt 中。
- 因此，子代理无需每次重新说明团队规范，就能按照统一标准开发。

**整个项目的唯一规范来源（Source of Truth）就是：**

```
.trellis/spec/
```

因此，现在把 Spec 完善好，后续所有 AI 编码任务都会持续受益。

---

## 完成后

当开发者确认：

- 所有待办项均已完成
- 所有 Spec 都包含真实示例（不是占位内容）

请引导开发者执行：

```bash
python ./.trellis/scripts/task.py finish
python ./.trellis/scripts/task.py archive 00-bootstrap-guidelines
```

执行 `archive` 后：

以后每位新加入项目的开发者，都不会再收到这个 Bootstrap 任务，而是会收到对应项目的：

```
00-join-<slug>
```

项目入门任务。

---

## 推荐开场白

> 欢迎使用 Trellis！刚刚执行的 `trellis init` 已经完成初始化，我会帮助你完善项目 Spec。这是一次性的配置工作，完成后，未来所有 AI 会话都会遵循团队规范，而不是生成通用风格的代码。
>
> 在开始之前，请问你的项目中是否已经存在规范文档（例如 `CLAUDE.md`、`.cursorrules`、`CONTRIBUTING.md` 等）？如果有，我可以优先导入其中的内容；如果没有，我们就直接扫描代码库，从实际代码中提取团队规范。
