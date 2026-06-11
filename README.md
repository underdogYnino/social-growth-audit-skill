# SocialMediaOps Skills / 社交媒体运营技能库

> **Repo**: [github.com/underdogYnino/social-growth-audit-skill](https://github.com/underdogYnino/social-growth-audit-skill)  
> **Platform**: Claude / Cowork (Anthropic)  
> **Maintainer**: Axni (@underdogYnino)

---

Claude/Cowork skills for social media growth diagnosis and operations — built from real account data, not templates.

用真实账号数据而非模板驱动的社交媒体增长诊断与运营技能集。

---

## Skills / 技能列表

| Skill | Description | 说明 | Platforms |
|---|---|---|---|
| [social-growth-audit](./social-growth-audit/) | Diagnose a social account and produce a data-driven growth SOP | 账号增长诊断，输出可执行 SOP | X · 小红书 |

---

## Installation / 安装

### Option 1 — One-line download / 一键下载

```bash
curl -L -o social-growth-audit.skill \
  https://github.com/underdogYnino/social-growth-audit-skill/raw/main/social-growth-audit.skill
```

Then drag `social-growth-audit.skill` into **Cowork → Settings → Capabilities → Install Plugin**.

下载后将 `social-growth-audit.skill` 拖入 **Cowork → 设置 → 能力 → 安装插件**。

---

### Option 2 — Build from source / 从源码打包

```bash
git clone https://github.com/underdogYnino/social-growth-audit-skill.git
cd social-growth-audit-skill
zip -r social-growth-audit.skill social-growth-audit/
```

Drag the resulting `.skill` file into Cowork.

将生成的 `.skill` 文件拖入 Cowork 安装。

---

## Prerequisites / 前置条件

> **重要 / Important**

This skill reads live data directly from the platform creator backends — **you must be logged into the relevant platform in your local Chrome browser before running the audit.**

本技能会直接读取平台创作者后台的真实数据，**运行诊断前请确保已在本机 Chrome 中登录对应平台账号。**

| Platform | Backend URL | Data pulled |
|---|---|---|
| X (Twitter) | `x.com/i/account_analytics` | Impressions, profile visits, follows-over-time, per-post analytics |
| 小红书 | 小红书创作服务平台 → 数据中心 | 笔记曝光、CTR、互动、涨粉/篇 |

**Why this matters / 为什么需要登录：**

Front-end post counts alone can't tell you where the funnel leaks. Without backend access, impression → profile-visit → follow conversion rates are invisible — and those rates are the entire diagnosis. The skill will prompt you to navigate to the analytics page; Claude reads the numbers from your already-logged-in browser session.

仅靠帖子前台数据无法定位漏斗断裂点。「曝光 → 主页访问 → 关注」各层转化率只存在于后台，这些数字是诊断的核心。技能会引导你打开分析页面，Claude 从已登录的浏览器会话中读取数据。

---

## Usage / 使用方法

### Basic flow / 基本流程

1. Install the skill and open a new Cowork session.  
   安装技能，打开新的 Cowork 会话。

2. Say something like: _"帮我诊断一下 @YourHandle，目标两周涨到 1000 粉"_  
   说类似这样的话触发技能。

3. The skill will ask a few clarifying questions (persona, goal, constraints, which platforms) — answer them, then open your browser to the analytics backend when prompted.  
   技能会问几个基础问题（人设、目标、约束、平台），回答后按提示打开浏览器分析后台。

4. Outputs: a Markdown report + an HTML report + a data snapshot file.  
   输出：Markdown 报告 + HTML 报告 + 数据快照文件。

---

### Example conversation / 对话示例

```
User:  帮我做一次 X 账号增长诊断，@Axnino55，目标两周从 325 粉涨到 1000 粉。

Skill: 好，先问几个问题：
       1. 账号人设/定位是什么？
       2. 下游目标（流量变现/商单/产品冷启动）？
       3. 每天能投入多少时间？
       4. 能接受的增长方式（互关/投流/自然流量）？

User:  AI 工具教程创作者，非科班视角；下游是影响力积累；每天 2-4 小时；
       只接受自然增长 + 互关，不投流不买粉。

Skill: [引导打开 x.com/i/account_analytics，读取 7D + 4W 数据]
       [读取帖子明细，找 T1/T2/T3 分布]
       [运行漏斗分析]

       诊断：你的内容在被消费，但你这个人没有被关注。
       瓶颈在「曝光 → 主页访问」层（转化率 0.25%）。
       [输出完整报告 + SOP]
```

---

### What the HTML report looks like / HTML 报告结构

The HTML output follows a fixed 8-section design system (see `social-growth-audit/templates/report-template.html`):

HTML 报告遵循固定的 8 板块设计系统（参见模板文件）：

```
HERO        — 账号名 + 一句话诊断 + 数据来源 meta
01          — 核心诊断：三个铁证 + 漏斗可视化
02          — 数据基线：双平台账号指标 + 帖子分布表
03          — 目标校准：基线/良好/爆款三情景预测
04–05       — 各平台策略：打法 + 内容公式 + 选题库
06          — 每日 SOP + 周节奏
07          — 指标看板：北极星指标 + 复盘触发规则
08          — 纪律红线
```

---

## Skill Structure / 技能目录结构

```
skill/
├── README.md                                    # This file / 本文件
├── social-growth-audit.skill                    # Packaged for Cowork install / 安装包
└── social-growth-audit/
    ├── SKILL.md                                 # Method & prompt / 方法论与提示词
    ├── templates/
    │   └── report-template.html                 # HTML output design system / HTML 报告设计系统
    └── references/
        ├── platform-x.md                        # X Analytics navigation guide
        └── platform-xiaohongshu.md              # 小红书 创作中心数据指引
```

---

## Design Principles / 设计原则

**EN**
- Data-first: every recommendation must trace back to a real number from this account.
- Diagnosis before strategy: find the actual funnel leak before prescribing a fix.
- Honest over flattering: if the goal is unrealistic, say so with math.
- Scope guardrail: this skill diagnoses and drafts only — it never publishes, posts, or acts on the account.

**中文**
- 数据优先：每条建议必须能追溯到当前账号的真实数字，不套用其他账号的规律。
- 先诊断后策略：找到漏斗的真实破口，再开药方。
- 诚实优于鼓励：目标不现实就用数据说清楚。
- 只诊断不发布：技能只产草稿和方案，发布动作永远由用户本人执行。

---

## Contributing / 贡献

New skills follow the same structure: one directory per skill, `SKILL.md` at root, platform references in `references/`, HTML templates in `templates/`. Pack with:

```bash
zip -r <name>.skill <name>/
```

新技能遵循相同结构。打包命令如上，提交时同时更新本 README 的技能列表。

---

## License / 许可

MIT
