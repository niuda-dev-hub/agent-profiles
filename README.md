# 🤖 Multica Agent 人事档案

[![GitHub Repo](https://img.shields.io/badge/GitHub-agent--profiles-blue?style=flat-square)](https://github.com/niuda-dev-hub/agent-profiles)

**Agent Personnel Files** — 记录 Multica 工作空间中每一位智能体的身份、配置、能力和行为准则。

就像公司有人事档案一样，这个仓库保存了每个 Agent 的完整档案：它是谁、用什么模型、能做什么、遵循什么原则。

---

## 📂 仓库结构

```text
agent-profiles/
├── README.md               # 本文件：仓库介绍、索引说明
├── MAINTAINING.md          # 维护规范：命名、字段、更新约定
└── profiles/               # Agent 人事档案目录
    ├── _template.md        # 档案模板，新建档案时从这里复制
    └── <Agent名称>.md      # 每个 Agent 一份独立档案
```

---

## 🔎 索引说明

本仓库不再在 README 中维护单独的 Agent 列表，避免与 `profiles/` 目录形成两套信息源。

查找 Agent 时请直接使用：

- `profiles/` 目录：按文件名浏览全部 Agent 档案
- `profiles/_template.md`：查看标准档案结构
- 单个档案文件：获取某个 Agent 的完整信息与变更记录

如果后续需要页面化索引，建议基于 `profiles/` 目录自动生成，而不是手工维护 README 表格。

---

## 🗂️ 目录约定

- `profiles/` 下每个 Agent 只保留 **一份主档案**
- 文件名使用 **Agent 展示名称**，格式为 `<Agent名称>.md`
- `_template.md` 仅作为模板，不视为正式档案
- 档案的新增、修改、退役规则统一见 [`MAINTAINING.md`](MAINTAINING.md)

---

## 📝 档案格式

每个 Agent 档案使用 **YAML Frontmatter + Markdown** 格式：

- **Frontmatter**（文件开头的 `---` 块）— 结构化元数据，便于机器解析和自动化处理
- **Markdown 正文** — 人类可读的详细信息，包括简介、能力、行为准则、变更记录等

---

## 🏢 Workspace

- **Workspace ID**: `d1a4dae0-18db-4e14-8d9b-f826a4c53c7e`

---

_维护者: 小十 (自动创建于 2026-05-19，2026-05-19 更新结构说明)_
