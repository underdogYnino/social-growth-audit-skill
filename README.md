# SocialMediaOps Skills / 社交媒体运营技能库

> **Repo**: [github.com/underdogYnino/social-growth-audit-skill](https://github.com/underdogYnino/social-growth-audit-skill)  
> **Platform**: Claude / Cowork (Anthropic)  
> **Maintainer**: Axni (@underdogYnino)

---

Claude/Cowork skills for social media growth diagnosis and operations — built from real account data, not templates.

用真实账号数据而非模板驱动的社交媒体增长诊断与运营技能集。

---

## Skills / 技能列表

| Skill | Description | 说明 |
|---|---|---|
| [social-growth-audit](./social-growth-audit/) | Diagnose a social account and produce a data-driven growth SOP | 账号增长诊断，输出可执行 SOP |

---

## How to Install / 如何安装

**In Cowork:**  
Settings → Capabilities → Install Plugin → drag the `.skill` file.

**在 Cowork 中：**  
设置 → 能力 → 安装插件 → 拖入对应的 `.skill` 文件。

---

## Skill Structure / 技能目录结构

```
skill/
├── README.md                        # This file / 本文件
├── <skill-name>.skill               # Packaged skill (zip) for Cowork install / 打包产物，供安装
└── <skill-name>/
    ├── SKILL.md                     # Skill prompt & method / 技能提示词与方法论
    └── references/                  # Platform-specific data guides / 平台数据指引
        ├── platform-x.md           # X (Twitter) analytics navigation
        └── platform-xiaohongshu.md # 小红书 创作服务平台数据指引
```

Each skill is self-contained. `SKILL.md` defines the method; `references/` tells the agent exactly where each metric lives in each platform's backend — so it reads real numbers instead of guessing.

每个技能自包含。`SKILL.md` 定义方法论；`references/` 告诉 Agent 每个指标在哪个平台后台的哪个位置——读真实数据，不靠猜测。

---

## Design Principles / 设计原则

**EN**  
- Data-first: every recommendation must trace back to a number from this account, not a pattern from another.  
- Diagnosis before strategy: find the actual leak in the funnel before prescribing a fix.  
- Honest over flattering: if the goal is unrealistic, say so with math.  
- Scope guardrail: these skills diagnose and draft only — they never publish, post, or act on the account.

**中文**  
- 数据优先：每条建议必须能追溯到当前账号的真实数字，不套用其他账号的规律。  
- 先诊断后策略：找到漏斗的真实破口，再开药方。  
- 诚实优于鼓励：目标不现实就用数据说清楚。  
- 只诊断不发布：技能只产草稿和方案，发布动作永远由用户本人执行。

---

## Contributing / 贡献

New skills should follow the same structure: one directory per skill, `SKILL.md` at root, platform references in `references/`. Pack with `zip -r <name>.skill <name>/` before committing the `.skill` file.

新技能遵循相同结构：每个技能一个目录，根目录放 `SKILL.md`，平台参考文件放 `references/`。提交前用 `zip -r <name>.skill <name>/` 打包 `.skill` 文件。

---

## License / 许可

MIT
