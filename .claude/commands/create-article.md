---
description: 根据提供的文章标题，创建符合命名规范的 Markdown 文章文件，包含基础 frontmatter 和文件结构
---

当用户调用 `/create-article <文章标题>` 时，执行以下步骤：

1. **提取标题**：从 slash command 参数中提取文章标题（去掉 `/create-article ` 前缀）。

2. **生成文件名**：
   - 将标题翻译为简洁、有意义的英文 slug（小写，单词之间用 `-` 连接，去掉标点符号）。
   - 保留标题中的英文单词和数字，适当简化过长的表达。
   - 例如：`给世界500强做医疗AI审核方案，我学到的5件事` → `lessons-from-fortune-500-medical-ai-review`
   - 文件名格式：`YYYY-MM-DD-<slug>.md`，使用当前日期。

3. **选择目录**：
   - 扫描项目中的文章目录（如 `03-domain-knowledge/healthcare-ai/`、`03-domain-knowledge/iot-integration/`、`01-enterprise-systems/erp-financial-ai/` 等）。
   - 如果目录明确（如标题含"医疗"则放入 healthcare-ai），直接选择；否则向用户展示可选目录并请其确认。

4. **创建文件**：
   - 使用 `Write` 工具创建 Markdown 文件，包含以下 frontmatter 和基础结构：

```markdown
---
title: <文章标题>
date: <当前日期 YYYY-MM-DD>
category: <根据目录推断的分类名>
tags: []
---

# <文章标题>

## 引言

（在此处补充项目背景与写作动机）

## 1. 

（待补充）

## 2. 

（待补充）

## 3. 

（待补充）

## 结语

（总结与展望）
```

5. **确认结果**：向用户报告创建成功的文件完整路径，并提示可以开始写作。

**注意**：如果 slug 生成有歧义，优先生成简洁、可读的版本；不要自行创建新目录，只使用已有的文章分类目录。
