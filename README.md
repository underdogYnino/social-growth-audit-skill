# 社交媒体运营技能库 · SocialMediaOps Skills

[中文](#中文) | [English](#english)

---

<a name="中文"></a>

## 项目简介

给 Claude / Cowork 用的社交媒体增长诊断技能集。核心逻辑：读取平台创作者后台的真实数据，定位漏斗断裂点，输出数据驱动的增长策略与可执行 SOP，而不是套模板给建议。

适用于：账号增长停滞、内容数据好但不涨粉、不知道该发什么、想建立可持续内容节奏的创作者。目前覆盖 X（Twitter）和小红书两个平台。

## 技能列表

| 技能 | 说明 | 平台 |
|---|---|---|
| [social-growth-audit](./social-growth-audit/) | 账号增长诊断，输出数据驱动的增长策略与可执行 SOP | X · 小红书 |

## 安装

**方式一：直接让 Agent 安装**

在 Cowork 会话中说：

> 帮我安装这个 skill：https://github.com/underdogYnino/social-growth-audit-skill.git

**方式二：一键下载**

```bash
curl -L -o social-growth-audit.skill \
  https://github.com/underdogYnino/social-growth-audit-skill/raw/main/social-growth-audit.skill
```

下载后将 `social-growth-audit.skill` 拖入 **Cowork → 设置 → 能力 → 安装插件**。

**方式三：从源码打包**

```bash
git clone https://github.com/underdogYnino/social-growth-audit-skill.git
cd social-growth-audit-skill
zip -r social-growth-audit.skill social-growth-audit/
```

将生成的 `.skill` 文件拖入 Cowork 安装。

## 前置条件

> **重要**：本技能会直接读取平台创作者后台的真实数据，**运行前请在本机 Chrome 中登录对应平台账号。**

| 平台 | 后台地址 | 读取内容 |
|---|---|---|
| X (Twitter) | `x.com/i/account_analytics` | 曝光、主页访问、关注趋势、帖子明细 |
| 小红书 | 小红书创作服务平台 → 数据中心 | 笔记曝光、CTR、互动、涨粉/篇 |

前台帖子数据无法定位漏斗断裂点。「曝光 → 主页访问 → 关注」各层转化率只存在于后台，这些数字是诊断的核心。技能会引导你打开分析页面，Claude 从已登录的浏览器会话中读取数据。

## 使用方法

安装后在 Cowork 新会话中说：

> 帮我做一次 X 账号诊断，账号：@xxxxxx，目标：两周涨到 xxxx 粉

> 帮我做一次小红书账号诊断，账号：xxxxxx，目标：一周涨 xxx 粉

如果已在本机 Chrome 登录账号，也可以直接提供主页 URL 加速诊断：

> 帮我做一次 X 账号诊断，我已在本地 Chrome 登录相应账号，账号个人资料页：「https://x.com/xxxxxx」，目标：两周涨到 xxxx 粉

输出：Markdown 报告 + HTML 报告 + 数据快照文件。HTML 报告遵循固定的 8 板块设计系统（见 `social-growth-audit/templates/report-template.html`）。

## 目录结构

```
├── README.md
├── social-growth-audit.skill          # Cowork 安装包
└── social-growth-audit/
    ├── SKILL.md                        # 方法论与提示词
    ├── templates/
    │   └── report-template.html        # HTML 报告设计系统
    └── references/
        ├── platform-x.md
        └── platform-xiaohongshu.md
```

## 设计原则

- 数据优先：每条建议必须能追溯到当前账号的真实数字，不套用其他账号的规律。
- 先诊断后策略：找到漏斗的真实破口，再开药方。
- 诚实优于鼓励：目标不现实就用数据说清楚。
- 只诊断不发布：技能只产草稿和方案，发布动作永远由用户本人执行。

## 贡献

新技能遵循相同结构：一个目录 + `SKILL.md` + `references/` + `templates/`。打包：

```bash
zip -r <name>.skill <name>/
```

提交时同步更新本 README 的技能列表。

## License

[MIT](./LICENSE)

---

<a name="english"></a>

## About

A collection of Claude / Cowork skills for social media growth diagnosis. The core idea: read real data from platform creator backends, locate the exact funnel leak, and produce a data-driven growth strategy with an executable SOP — not generic advice from a template.

Built for creators whose content gets engagement but not followers, who don't know what to post, or who want a sustainable content rhythm. Currently covers X (Twitter) and 小红书 (Xiaohongshu / RED).

## Skills

| Skill | Description | Platforms |
|---|---|---|
| [social-growth-audit](./social-growth-audit/) | Diagnose a social account and produce a data-driven growth SOP | X · 小红书 |

## Installation

**Option 1 — Ask the Agent**

In a Cowork session, say:

> Install this skill for me: https://github.com/underdogYnino/social-growth-audit-skill.git

**Option 2 — One-line download**

```bash
curl -L -o social-growth-audit.skill \
  https://github.com/underdogYnino/social-growth-audit-skill/raw/main/social-growth-audit.skill
```

Drag `social-growth-audit.skill` into **Cowork → Settings → Capabilities → Install Plugin**.

**Option 3 — Build from source**

```bash
git clone https://github.com/underdogYnino/social-growth-audit-skill.git
cd social-growth-audit-skill
zip -r social-growth-audit.skill social-growth-audit/
```

Drag the resulting `.skill` file into Cowork.

## Prerequisites

> **Important**: This skill reads live data from platform creator backends. **You must be logged into the relevant platform in your local Chrome browser before running the audit.**

| Platform | Backend URL | Data pulled |
|---|---|---|
| X (Twitter) | `x.com/i/account_analytics` | Impressions, profile visits, follows-over-time, per-post analytics |
| 小红书 | Creator Service Platform → Data Center | Note impressions, CTR, engagement, followers-per-post |

Front-end post counts can't tell you where the funnel leaks. The skill prompts you to open the analytics page; Claude reads the numbers from your already-logged-in browser session.

## Usage

After installing, open a new Cowork session and say:

> Run a growth audit for my X account @xxxxxx, goal: reach xxxx followers in 2 weeks

> Run a growth audit for my 小红书 account xxxxxx, goal: +xxx followers in 1 week

If you're already logged into the platform in Chrome, you can include the profile URL to speed things up:

> Run a growth audit for my X account. I'm already logged into Chrome. Profile page:「https://x.com/xxxxxx」. Goal: xxxx followers in 2 weeks

Outputs: Markdown report + HTML report + data snapshot file.

## Design Principles

- Data-first: every recommendation traces back to a real number from this account.
- Diagnosis before strategy: find the actual funnel leak before prescribing a fix.
- Honest over flattering: if the goal is unrealistic, say so with math.
- Scope guardrail: diagnoses and drafts only — never publishes or acts on the account.

## Contributing

Each skill gets its own directory with `SKILL.md`, `references/`, and `templates/`. Pack with:

```bash
zip -r <name>.skill <name>/
```

Update this README's skill table when adding a new skill.

## License

[MIT](./LICENSE)
