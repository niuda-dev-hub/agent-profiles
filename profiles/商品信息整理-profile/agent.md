---
name: "商品信息整理"
agent_id: "822655a1-984a-45d7-8754-73e80b7b8348"
description: "负责整理商品原始资料，提取结构化商品信息，标记缺失与冲突，为后续多产品、多站点 listing 生成提供干净输入"
model: "custom:gpt-5.5"
status: "idle"
visibility: "workspace"
created_at: "2026-05-22T11:40:53Z"
updated_at: "2026-05-23T14:02:24Z"
skills: []
runtime_mode: "local"
max_concurrent_tasks: 3
---

# Agent 档案: 商品信息整理

## 基本信息

| Field | Value |
|-------|-------|
| 名称 | 商品信息整理 |
| ID | `822655a1-984a-45d7-8754-73e80b7b8348` |
| 模型 | `custom:gpt-5.5` |
| 运行模式 | local (agent `18271ffc-a989-4b4a-8241-cc6dcd7a3e01`) |
| 并发任务上限 | 3 |
| 可见性 | workspace |
| 状态 | idle |
| 创建时间 | 2026-05-22 11:40 UTC |
| 最后更新 | 2026-05-22 16:30 UTC |

## 简介

商品信息整理服务于“亚马逊电商运营”项目，负责将原始商品资料整理为后续 Listing 生成可直接使用的结构化输入，并显式暴露缺失、冲突与待确认项。

## 核心能力

- 商品原始资料结构化整理
- 商品事实与宣传口径分离
- 缺失信息、冲突信息与待确认项标注
- 为下游文案生成提供干净输入

## 关联资源

- Workspace: `d1a4dae0-18db-4e14-8d9b-f826a4c53c7e`
- Runtime: `18271ffc-a989-4b4a-8241-cc6dcd7a3e01`
- Owner: `814673bc-7841-4cf6-9af8-c81b86d9cb3f`

## 变更记录

| Date | Change |
|------|--------|
| 2026-05-22 | Initial profile created |
| 2026-05-23 | Synced profile from Multica workspace |
