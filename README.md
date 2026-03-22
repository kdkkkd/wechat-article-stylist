# WeChat Article Stylist

一个面向 Codex 的公众号写作与排版 skill，用来生成更适合微信公众号发布的文章成稿。

它不只是“写一篇文章”，而是会尽量按照公众号的阅读习惯，直接交付更完整的发布包，包括标题备选、封面副标题、摘要、正文排版稿，以及按需补充的金句、互动引导和配图建议。

## Features

- 提供 3 个标题备选，增强点击率空间
- 输出封面副标题和摘要，方便直接用于公众号发布
- 按手机端阅读习惯组织正文，强调短段落、留白和层次
- 支持干货型、故事型、观点型、治愈型、转化型、AI 知识号等常见风格
- 内置排版模块、标题公式和文章结构套路，方便稳定复用

## Repository Structure

```text
.
├─ README.md
├─ .gitignore
├─ examples/
│  └─ sample-prompts.md
└─ wechat-article-stylist/
   ├─ SKILL.md
   ├─ agents/
   │  └─ openai.yaml
   ├─ references/
   │  ├─ layout-recipes.md
   │  └─ voice-and-structure.md
   └─ assets/
      └─ wechat-article-template.md
```

## What The Skill Produces

默认情况下，skill 会优先交付：

- 3 个标题备选
- 1 个封面副标题
- 1 段摘要
- 1 篇适合公众号编辑器粘贴的正文排版稿
- 1 段文末互动引导

如果任务适合传播或转化，还会补充：

- 金句摘录
- 配图建议
- 朋友圈转发文案

## Use Cases

适合这些场景：

- 写公众号首发文章
- 把已有草稿改成更适合公众号发布的版本
- 优化标题、摘要和开头，提高可读性
- 把专业内容改写成更适合手机端阅读的排版稿
- 为品牌号、个人 IP、知识号、情感号准备更完整的内容发布稿
- 细化 AI 知识博主公众号风格，支持模型、Agent、工作流、工具链类内容
- 可以自然纳入 OpenClaw 等可调用工具/智能体作为案例或工作流节点

## How To Use

把 `wechat-article-stylist` 文件夹放到你的 Codex skills 目录中，然后在任务里显式调用这个 skill。

示例：

```text
Use $wechat-article-stylist to write a WeChat public account article about why deep work matters for young professionals.
```

也可以用中文直接提需求，例如：

```text
使用 $wechat-article-stylist，写一篇关于“普通人如何建立稳定输出习惯”的公众号文章，风格真诚、有质感，适合个人成长类账号。
```

更多示例见 [sample-prompts.md](/D:/gzh/examples/sample-prompts.md)。

## Skill Design

这个 skill 的核心目标是让输出同时满足三件事：

- 有信息密度，而不是空泛套话
- 有阅读节奏，而不是一整屏一整屏的大段文字
- 有发布完成度，而不是只给一份“还需要二次加工”的半成品

为此，skill 内部分成三层：

- `SKILL.md`：定义触发条件、写作流程、排版规则和默认交付标准
- `references/`：提供标题公式、结构模板和排版积木
- `AI 知识号`：补充适合 AI 创作者账号的标题、结构、口吻和实操模板
- `assets/`：提供可快速套用的成稿模板

## Included Files

- [SKILL.md](/D:/gzh/wechat-article-stylist/SKILL.md)
- [openai.yaml](/D:/gzh/wechat-article-stylist/agents/openai.yaml)
- [layout-recipes.md](/D:/gzh/wechat-article-stylist/references/layout-recipes.md)
- [voice-and-structure.md](/D:/gzh/wechat-article-stylist/references/voice-and-structure.md)
- [wechat-article-template.md](/D:/gzh/wechat-article-stylist/assets/wechat-article-template.md)

## Notes

- 当前仓库聚焦 skill 本体与说明文档，没有绑定特定平台 API。
- 如果后续你希望把它升级成“带品牌风格模板”的版本，可以继续补充品牌语气、固定栏目结构、配色和封面文案规范。
