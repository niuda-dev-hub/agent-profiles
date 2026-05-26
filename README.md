# 🤖 Multica Agent 人事档案

[![GitHub Repo](https://img.shields.io/badge/GitHub-agent--profiles-blue?style=flat-square)](https://github.com/niuda-dev-hub/agent-profiles)

**Agent Personnel Files** — 记录 Multica 工作空间中每一位智能体的身份、配置、技能资产和行为准则。

这个仓库现在采用“**一个 agent 一个 profile 文件夹**”的结构：把结构化档案、人格/原则描述以及附件拆开保存，便于后续持续扩展，同时继续保持 README 不承担手工索引职责。

---

## 📂 仓库结构

```text
agent-profiles/
├── README.md
├── MAINTAINING.md
├── profiles/
│   ├── _template/
│   │   ├── agent.md
│   │   ├── soul.md
│   │   └── assets/
│   ├── 初八-profile/
│   │   ├── agent.md
│   │   ├── soul.md
│   │   └── assets/
│   ├── 初九-profile/
│   │   ├── agent.md
│   │   ├── soul.md
│   │   └── assets/
│   ├── 商品信息整理-profile/
│   │   ├── agent.md
│   │   ├── soul.md
│   │   └── assets/
│   ├── 工作区巡视官-profile/
│   │   ├── agent.md
│   │   ├── soul.md
│   │   └── assets/
│   ├── 小十-profile/
│   │   ├── agent.md
│   │   ├── soul.md
│   │   └── assets/
│   ├── 招聘专员-profile/
│   │   ├── agent.md
│   │   ├── soul.md
│   │   └── assets/
│   ├── 日本站-Listing-生成-profile/
│   │   ├── agent.md
│   │   ├── soul.md
│   │   └── assets/
│   ├── 欧美多语种-Listing-生成-profile/
│   │   ├── agent.md
│   │   ├── soul.md
│   │   └── assets/
│   ├── 竞品分析与关键词筛选-profile/
│   │   ├── agent.md
│   │   ├── soul.md
│   │   └── assets/
│   ├── 高级巡视员-profile/
│   │   ├── agent.md
│   │   ├── soul.md
│   │   └── assets/
│   └── 轻量主管-profile/
│       ├── agent.md
│       ├── soul.md
│       └── assets/
└── skills/
    ├── imported/
    └── authored/
```

---

## 🧭 索引说明

本仓库不再在 README 中维护单独的 Agent 清单，避免与 `profiles/` 目录形成两套信息源。

- `profiles/`：每个 agent 一份独立目录，保存该 agent 的完整档案
- `profiles/<agent>-profile/agent.md`：结构化身份、模型、运行信息、能力、资源
- `profiles/<agent>-profile/soul.md`：人格、原则、协作风格、长期行为特征
- `profiles/<agent>-profile/assets/`：可选附件，例如截图、补充文档、导出材料
- `skills/imported/`：安装、导入或共享得到的 skills
- `skills/authored/`：agent 在工作中自行沉淀、总结出来的 skills

如果后续需要页面化索引，建议基于 `profiles/` 目录自动生成，而不是继续手工维护 README 表格。

---

## 📝 新增或维护 Agent 档案

1. 复制 `profiles/_template/` 为新的 `<Agent名称>-profile/`
2. 填写 `agent.md` 与 `soul.md`
3. 如有附件，放到同目录 `assets/`
4. 如需登记技能资产，把 skill 文件放到 `skills/imported/` 或 `skills/authored/`
5. 提交并推送改动

详细字段约定、命名规则和更新要求见 [`MAINTAINING.md`](MAINTAINING.md)。

---

## 🏢 Workspace

- **Workspace ID**: `d1a4dae0-18db-4e14-8d9b-f826a4c53c7e`

---

_维护者: 小十 (自动创建于 2026-05-19，2026-05-19 更新结构说明)_
