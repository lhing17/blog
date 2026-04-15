---
description: 根据最近的 git 提交记录和工程内容，自动分析并更新 README 文档
---

当用户调用 `/update-readme` 时，执行以下步骤：

1. **收集工程信息**：
   - 使用 `Bash` 工具执行 `git log --oneline -n 20` 获取最近的提交记录
   - 使用 `Glob` 或 `Read` 工具浏览项目根目录下的关键文件（如 `package.json`、`Cargo.toml`、`pyproject.toml` 等），了解项目类型和结构
   - 阅读当前 `README.md`（如果存在）以了解现有内容

2. **分析变更内容**：
   - 根据 git 提交记录总结近期的功能新增、修改、修复或重构
   - 结合工程结构判断是否需要补充项目介绍、安装说明、使用方式、贡献指南等内容

3. **生成更新后的 README**：
   - 基于现有 README 和最新变更，生成更新后的 README 内容
   - 使用 `Write` 或 `Edit` 工具将更新后的内容写入 `README.md`

**注意**：
- 在覆盖 `README.md` 前，先向用户展示变更摘要并征得确认
- 保留 README 中已有的品牌描述、徽章链接等无需更新的内容
- 如果项目中不存在 `README.md`，则根据工程结构新建一份基础 README
