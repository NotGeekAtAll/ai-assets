# Commit Work
创建高质量、生产就绪的 Git 提交的综合技能，让提交易于审查、安全可上线，并遵循最佳实践。

## 目的
此技能通过以下方式帮助您创建精心设计的 Git 提交：
- 确保只包含预期的更改
- 将工作拆分为逻辑清晰的提交
- 编写清晰、描述性的提交信息，解释“改了什么”和“为什么改”
- 遵循 Conventional Commits 格式
- 防止常见错误（密钥、调试代码、无关更改）

## 何时使用
当您需要以下操作时使用此技能：
- 使用正确的暂存和审查流程提交工作
- 撰写有意义的提交信息
- 将混合更改拆分为多个逻辑提交
- 遵循 Conventional Commits 格式
- 确保提交适合审查并安全合并

**触发短语：**
- "commit this work"
- "create a commit"
- "split these changes into commits"
- "help me commit"
- "write a commit message"

## 工作原理
该技能遵循严格的 8 步工作流程：
1. **检查** - 使用 `git status` 和 `git diff` 查看工作区
2. **决定边界** - 判断是否需要将更改拆分为多个提交
3. **选择性暂存** - 使用补丁暂存（`git add -p`）进行精细控制
4. **审查已暂存更改** - 使用 `git diff --cached` 验证
5. **描述更改** - 用 1-2 句话说明“改了什么”和“为什么改”
6. **编写信息** - 按照 Conventional Commits 格式撰写提交信息
7. **验证** - 在提交前运行相关测试/检查
8. **重复** - 持续操作直到工作区干净

## 关键特性
### 智能提交拆分
自动识别何时需要拆分提交，包括：
- 功能 vs 重构
- 后端 vs 前端
- 格式化 vs 逻辑更改
- 测试 vs 生产代码
- 依赖升级 vs 行为变更

### Conventional Commits 格式
所有提交均遵循标准格式：
```
type(scope): 简短摘要
详细正文，解释改了什么和为什么改。
BREAKING CHANGE: 如果适用
```

### 安全检查
审查已暂存更改，检查是否存在：
- 密钥或令牌
- 意外的调试日志
- 无关的格式化更改
- 混合或范围过大的提交

### 补丁暂存
在单个文件内需要拆分更改时，广泛使用 `git add -p` 进行细粒度控制。

## 使用示例
### 示例 1：简单单次提交
```bash
# 用户指令："commit this bugfix"
# 技能工作流程：
git status
git diff
git add src/api/auth.js
git diff --cached
git commit -m "fix(auth): 解决 token 过期边缘情况

之前 token 在过期前 1 秒内会因时钟偏差验证失败。
现在增加了 5 秒的宽限期。"
```

### 示例 2：拆分混合更改
```bash
# 用户有：格式化更改 + 新功能 + 测试更新
# 技能创建 3 个提交：
# 提交 1: chore: 使用 prettier 格式化代码
# 提交 2: feat(api): 添加用户资料接口
# 提交 3: test: 为资料接口添加测试覆盖率
# 使用 git add -p 进行选择性暂存
```

### 示例 3：交互式补丁暂存
```bash
# 单个文件混杂了重构和 bugfix
git add -p src/components/Header.js
# 只暂存 bugfix 部分用于第一个提交
git commit -m "fix(ui): 修复移动端菜单 z-index 问题"
git add src/components/Header.js
# 暂存重构部分用于第二个提交
git commit -m "refactor(ui): 将菜单逻辑提取为自定义 Hook"
```

## 输入
技能可能会询问：
- **提交策略**：单个提交还是多个逻辑提交？
- **提交风格**：Conventional Commits（默认强制使用）
- **项目规则**：主题长度上限、必需的作用域等。

若未提供，则默认采用：
- 更改无关时拆分为多个小提交
- Conventional Commits 格式
- 标准最佳实践

## 交付物
运行完成后，技能提供：
- 最终使用的提交信息
- 每个提交的简短摘要（改了什么 / 为什么改）
- 用于暂存和审查的命令
- 测试/验证结果

## 最佳实践
1. **暂存前先审查** - 始终先检查 `git diff`
2. **有意暂存** - 绝不使用 `git add .` 或 `git add -A`
3. **使用补丁模式** - 对混合更改充分利用 `git add -p`
4. **验证已暂存内容** - 提交前检查 `git diff --cached`
5. **保持提交专注** - 每个提交只包含一个逻辑变更
6. **为审查者写作** - 解释“什么”和“为什么”，而非具体实现细节
7. **提交前测试** - 每个提交后运行相关检查

## 相关资源
- 参考 `references/commit-message-template.md` 获取信息模板
- 使用 Conventional Commits 规范：https://www.conventionalcommits.org/
- 与标准 Git 工作流和钩子集成

## 注意事项
- 此技能强制使用 Conventional Commits 格式
- 鼓励小而专注的提交，而非大型单体提交
- 广泛使用补丁暂存（`git add -p`）实现精细控制
- 每个提交都应通过基本验证（测试、lint、构建）
- 目标是创建易于审查、可二分、可 cherry-pick 的安全提交
