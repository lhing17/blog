---
description: 在 .claude/commands 目录下创建一个新的 slash command Markdown 文件，包含基础 frontmatter 和描述模板
---

当用户调用 `/create-slash-command <command-name>` 时，执行以下步骤：

1. **提取名称**：从 slash command 参数中提取命令名称（去掉 `/create-slash-command ` 前缀）。
   - 名称应仅包含小写字母、数字和连字符 `-`。
   - 如果名称包含空格或其他字符，自动转换为 `kebab-case`。

2. **校验目录**：确认当前目录下存在 `.claude/commands` 目录。如果不存在，使用 `Bash` 工具创建它：`mkdir -p .claude/commands`。

3. **创建文件**：在 `.claude/commands/` 下创建 `<command-name>.md` 文件，包含以下 frontmatter 和基础结构：

```markdown
---
description: 在此处填写 slash command 的简要描述
---

当用户调用 `/<command-name> <参数>` 时，执行以下步骤：

1. **步骤一**：
   （在此处描述第一步操作）

2. **步骤二**：
   （在此处描述第二步操作）

3. **步骤三**：
   （在此处描述第三步操作）

**注意**：
- （在此处补充额外的注意事项或约束条件）
```

4. **确认结果**：向用户报告创建成功的文件完整路径，并提示可以开始编辑描述内容。

**注意**：如果同名文件已存在，提示用户是否覆盖，避免误删已有的 slash command。
