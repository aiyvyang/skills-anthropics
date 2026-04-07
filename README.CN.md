> **注意：** 本仓库包含 Anthropic 为 Claude 实现的技能集。有关 Agent Skills 标准的详细信息，请参阅 [agentskills.io](http://agentskills.io)。

# 技能（Skills）

技能是包含指令、脚本和资源的文件夹，Claude 可以动态加载这些内容以提升在特定任务上的表现。技能教会 Claude 如何以可重复的方式完成特定任务，例如按照公司品牌规范创建文档、使用组织特定工作流程分析数据，或自动化个人任务。

更多信息请参阅：
- [什么是技能？](https://support.claude.com/en/articles/12512176-what-are-skills)
- [在 Claude 中使用技能](https://support.claude.com/en/articles/12512180-using-skills-in-claude)
- [如何创建自定义技能](https://support.claude.com/en/articles/12512198-creating-custom-skills)
- [为智能体配备应对现实世界的技能](https://anthropic.com/engineering/equipping-agents-for-the-real-world-with-agent-skills)

# 关于本仓库

本仓库包含展示 Claude 技能系统可能性的示例技能，涵盖创意应用（艺术、音乐、设计）、技术任务（Web 应用测试、MCP 服务器生成）到企业工作流（通信、品牌管理）等多个领域。

每个技能都自成一体，存放在独立文件夹中，包含一个 `SKILL.md` 文件，其中有 Claude 使用的指令和元数据。浏览这些技能可以为您创建自己的技能提供灵感，或帮助您理解不同的模式和方法。

本仓库中的许多技能是开源的（Apache 2.0 协议）。我们还在 [`skills/docx`](./skills/docx)、[`skills/pdf`](./skills/pdf)、[`skills/pptx`](./skills/pptx) 和 [`skills/xlsx`](./skills/xlsx) 子文件夹中收录了支撑 [Claude 文档能力](https://www.anthropic.com/news/create-files) 的文档创建与编辑技能。这些技能属于源码可查但非开源，我们希望将其作为更复杂且已在生产环境中运行的技能参考，分享给开发者。

## 免责声明

**这些技能仅用于演示和教育目的。** 虽然其中部分功能可能已在 Claude 中可用，但您从 Claude 实际获得的实现和行为可能与这些技能中展示的有所不同。这些技能旨在说明各种模式和可能性。在将其用于关键任务之前，请务必在您自己的环境中充分测试。

# 技能集

- [./skills](./skills)：创意与设计、开发与技术、企业与通信、文档技能的示例
- [./spec](./spec)：Agent Skills 规范
- [./template](./template)：技能模板

# 在 Claude Code、Claude.ai 和 API 中试用

## Claude Code

您可以在 Claude Code 中运行以下命令，将本仓库注册为插件市场：

```
/plugin marketplace add anthropics/skills
```

然后，安装特定技能集：
1. 选择 `浏览并安装插件`
2. 选择 `anthropic-agent-skills`
3. 选择 `document-skills` 或 `example-skills`
4. 选择 `立即安装`

或者，直接通过以下命令安装插件：

```
/plugin install document-skills@anthropic-agent-skills
/plugin install example-skills@anthropic-agent-skills
```

安装插件后，只需提及即可使用相应技能。例如，从市场安装 `document-skills` 插件后，可以让 Claude Code 执行类似操作："使用 PDF 技能提取 `path/to/some-file.pdf` 中的表单字段。"

## Claude.ai

这些示例技能已全部对 Claude.ai 付费套餐开放。

要使用本仓库中的任意技能或上传自定义技能，请按照[在 Claude 中使用技能](https://support.claude.com/en/articles/12512180-using-skills-in-claude#h_a4222fa77b)中的说明操作。

## Claude API

您可以通过 Claude API 使用 Anthropic 预构建的技能，也可以上传自定义技能。详情请参阅 [技能 API 快速入门](https://docs.claude.com/en/api/skills-guide#creating-a-skill)。

# 创建基础技能

创建技能非常简单——只需一个包含 `SKILL.md` 文件的文件夹，文件中含有 YAML 前置元数据和指令即可。您可以使用本仓库中的 **template-skill** 作为起点：

```markdown
---
name: my-skill-name
description: 清晰描述该技能的功能及使用场景
---

# 我的技能名称

[在此添加 Claude 激活该技能时遵循的指令]

## 示例
- 使用示例 1
- 使用示例 2

## 指南
- 指南 1
- 指南 2
```

前置元数据仅需两个字段：
- `name` —— 技能的唯一标识符（小写字母，空格用连字符代替）
- `description` —— 对技能功能及使用场景的完整描述

下方的 Markdown 内容包含 Claude 将遵循的指令、示例和指南。更多详情请参阅[如何创建自定义技能](https://support.claude.com/en/articles/12512198-creating-custom-skills)。

# 合作伙伴技能

技能是教会 Claude 更好地使用特定软件的好方法。如果我们看到来自合作伙伴的优秀示例技能，可能会在此进行推荐：

- **Notion** - [适用于 Claude 的 Notion 技能](https://www.notion.so/notiondevs/Notion-Skills-for-Claude-28da4445d27180c7af1df7d8615723d0)
