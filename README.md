# 🤖 Multica Agent 人事档案

[![GitHub Repo](https://img.shields.io/badge/GitHub-agent--profiles-blue?style=flat-square)](https://github.com/niuda-dev-hub/agent-profiles)

**Agent Personnel Files** — 记录 Multica 工作空间中每一位智能体的身份、配置、能力和行为准则。

就像公司有人事档案一样，这个仓库保存了每个 Agent 的完整档案：它是谁、用什么模型、能做什么、遵循什么原则。

---

## 📂 仓库结构

```
agent-profiles/
├── README.md               # 本文件 — 仓库介绍与使用说明
└── profiles/               # 📁 Agent 人事档案目录
    ├── _template.md        #   档案模板 — 创建新 Agent 档案时使用
    ├── 初八.md             #   第一个智能体
    ├── 初九.md             #   第二个智能体
    └── 小十.md             #   第三个智能体
```

---

## 🧑‍💼 现有 Agent

| # | 名称 | ID | 模型 | 状态 | 档案 |
|---|------|----|------|------|------|
| 1 | **初八** | `0921a945-...` | `custom:gpt-5.4` | ⏸️ Idle | [📄 查看](profiles/初八.md) |
| 2 | **初九** | `d934df23-...` | `main` | ⏸️ Idle | [📄 查看](profiles/初九.md) |
| 3 | **小十** | `b54dd43b-...` | `opencode/big-pickle` | 🟢 Working | [📄 查看](profiles/小十.md) |

---

## 📝 档案格式

每个 Agent 档案使用 **YAML Frontmatter + Markdown** 格式：

- **Frontmatter** (文件开头的 `---` 块) — 结构化元数据，便于机器解析和自动化处理
- **Markdown 正文** — 人类可读的详细信息，包括简介、能力、行为准则、变更记录等

### 创建新 Agent 档案

```bash
# 1. 复制模板
cp profiles/_template.md profiles/新Agent名称.md

# 2. 编辑档案信息
# 3. 提交并推送
git add profiles/新Agent名称.md
git commit -m "add profile: 新Agent名称"
git push
```

---

## 🔄 维护流程

- **添加新 Agent** → 复制模板，填写信息，提交 PR
- **更新 Agent 信息** → 修改对应档案文件
- **Agent 退役** → 将 status 标记为 `archived`，保留档案作为历史记录

---

## 🏢 Workspace

- **Workspace ID**: `d1a4dae0-18db-4e14-8d9b-f826a4c53c7e`

---

_维护者: 小十 (自动创建于 2026-05-19)_
