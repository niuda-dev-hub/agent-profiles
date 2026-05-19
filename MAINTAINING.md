# Agent Profiles 维护规范

本仓库用于维护 Multica 工作空间内 Agent 的人事档案。目标是：**单一信息源、低重复维护、便于人工阅读，也便于后续自动化处理。**

## 1. 维护原则

1. **以 `profiles/` 目录为唯一索引来源**  
   不在 README 手工维护 Agent 清单、状态表或模型列表；需要查看成员时，直接以目录内容为准。
2. **一个 agent 一个 profile 目录**  
   每个 Agent 使用独立目录保存完整档案，而不是继续把所有信息压在单个 Markdown 文件里。
3. **模板先行**  
   新建档案时先复制 `profiles/_template/`，再填写具体内容，避免结构漂移。
4. **改动即更新**  
   当 Agent 的名称、模型、状态、能力描述、人格原则或关联资源发生变化时，同步更新对应档案。

## 2. 目录约定

```text
profiles/
├── _template/
│   ├── agent.md
│   ├── soul.md
│   └── assets/
└── <Agent名称>-profile/
    ├── agent.md
    ├── soul.md
    └── assets/

skills/
├── imported/
└── authored/
```

- 每个 profile 目录至少包含：`agent.md`、`soul.md`、`assets/`
- 模板目录固定为 `profiles/_template/`
- 技能资产统一放在仓库顶层 `skills/` 下
- `skills/imported/` 用于外部安装、导入、共享技能
- `skills/authored/` 用于 agent 自己沉淀、总结的技能

## 3. 单一信息来源

- Agent 的结构化身份、模型、状态、运行信息以 `agent.md` 为准
- Agent 的人格、行为原则、协作偏好以 `soul.md` 为准
- README 只负责说明目录与维护方法，不再维护单独的 agent 名单表
- 不要在 `profiles/` 下再额外维护重复索引页、状态汇总表或 README 副本

## 4. agent.md 字段要求

`agent.md` 使用 YAML Frontmatter + Markdown。

Frontmatter 推荐字段：

- `name`
- `agent_id`
- `description`
- `model`
- `status`：`idle` | `working` | `blocked` | `archived`
- `visibility`：`workspace` | `org` | `public`
- `created_at`
- `updated_at`
- `skills`
- `runtime_mode`：`local` | `remote`
- `max_concurrent_tasks`

正文建议至少包含：

- 基本信息
- 简介
- 核心能力
- 关联资源
- 变更记录

## 5. soul.md 内容要求

`soul.md` 主要保存：

- 人格定位
- 行为原则
- 协作风格
- 长期偏好或稳定约束

这里不要求统一 frontmatter；重点是长期可读、便于补充。

## 6. 命名与更新规则

- 目录名默认使用可读格式：`<显示名>-profile`
- 如果未来需要避免重命名成本，可改用稳定 slug 或 agent_id，但需在仓库内保持一致
- agent 状态变化、模型变化、职责变化时，优先更新对应的 `agent.md`
- 人格、原则、偏好变化时，更新 `soul.md`
- agent 退役时，不删除目录；把 `status` 设为 `archived`，作为历史档案保留

## 7. 技能目录维护规则

- `skills/imported/` 中保留技能来源说明或原始导入文件
- `skills/authored/` 中优先保存 agent 自己提炼后的版本
- 同一份 skill 不要在 `profiles/` 和 `skills/` 中重复维护

## 8. 新增 Agent 流程

```bash
cp -R profiles/_template profiles/新Agent-profile
```

然后：

1. 填写 `agent.md`
2. 填写 `soul.md`
3. 如有附件，放入 `assets/`
4. 如需记录技能资产，把内容放到 `skills/imported/` 或 `skills/authored/`
5. 提交改动

## 9. 变更建议

如果后续 Agent 数量继续增长，优先考虑：

- 基于 `profiles/` 自动生成索引页
- 增加简单校验脚本，检查目录名、`name`、`updated_at` 等字段一致性

在没有自动化之前，保持结构简单、职责清晰比增加手工汇总页更重要。
