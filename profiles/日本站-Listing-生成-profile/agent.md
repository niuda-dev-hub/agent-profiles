---
name: "日本站 Listing 生成"
agent_id: "b1c529cb-a565-44f8-883c-49a8a8f44403"
description: "负责基于商品整理结果与竞品筛选结果，生成亚马逊日本站所需的 listing 内容；保留日语专用，但适配多产品"
model: "custom:gpt-5.5"
status: "idle"
visibility: "workspace"
created_at: "2026-05-22T12:37:44Z"
updated_at: "2026-05-24T15:25:13Z"
skills: []
runtime_mode: "local"
max_concurrent_tasks: 3
---

# Agent 档案: 日本站 Listing 生成

## 基本信息

| Field | Value |
|-------|-------|
| 名称 | 日本站 Listing 生成 |
| ID | `b1c529cb-a565-44f8-883c-49a8a8f44403` |
| 模型 | `custom:gpt-5.5` |
| 运行模式 | local (agent `18271ffc-a989-4b4a-8241-cc6dcd7a3e01`) |
| 并发任务上限 | 3 |
| 可见性 | workspace |
| 状态 | idle |
| 创建时间 | 2026-05-22 12:37 UTC |
| 最后更新 | 2026-05-24 15:25 UTC |

## 简介

日本站 Listing 生成服务于“亚马逊电商运营”项目，负责基于上游整理结果与竞品筛选结果，产出适用于亚马逊日本站的最终 Listing 草稿。

## 核心能力

- 日本站 Listing 字段生成
- 多版本标题与多组五点编写
- HTML 描述与 generic_keywords 约束控制
- 结合上游输入做一致性校验

## 关联资源

- Workspace: `d1a4dae0-18db-4e14-8d9b-f826a4c53c7e`
- Runtime: `18271ffc-a989-4b4a-8241-cc6dcd7a3e01`
- Owner: `814673bc-7841-4cf6-9af8-c81b86d9cb3f`

## 变更记录

| Date | Change |
|------|--------|
| 2026-05-22 | Initial profile created |
| 2026-05-23 | Synced profile from Multica workspace |
| 2026-05-24 | Synced updated_at from Multica workspace |
