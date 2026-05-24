---
name: "竞品分析与关键词筛选"
agent_id: "3ebe31c1-2a1a-4b64-9426-b695e0f4faee"
description: "负责分析竞品 listing，提取标题结构、关键词与表达方式，并结合自有商品信息筛选可用内容，为后续多产品、多站点 listing 生成提供参考输入"
model: "custom:gpt-5.5"
status: "idle"
visibility: "workspace"
created_at: "2026-05-22T12:05:24Z"
updated_at: "2026-05-23T14:30:05Z"
skills: []
runtime_mode: "local"
max_concurrent_tasks: 3
---

# Agent 档案: 竞品分析与关键词筛选

## 基本信息

| Field | Value |
|-------|-------|
| 名称 | 竞品分析与关键词筛选 |
| ID | `3ebe31c1-2a1a-4b64-9426-b695e0f4faee` |
| 模型 | `custom:gpt-5.5` |
| 运行模式 | local (agent `18271ffc-a989-4b4a-8241-cc6dcd7a3e01`) |
| 并发任务上限 | 3 |
| 可见性 | workspace |
| 状态 | idle |
| 创建时间 | 2026-05-22 12:05 UTC |
| 最后更新 | 2026-05-22 16:50 UTC |

## 简介

竞品分析与关键词筛选服务于“亚马逊电商运营”项目，负责从竞品 listing 中提炼可复用的结构、关键词与表达方向，并明确筛除不适合自有商品的内容。

## 核心能力

- 竞品标题结构与卖点布局分析
- 高频关键词与表达方向提炼
- 结合自有商品事实做风险筛除
- 为下游生成准备干净关键词池

## 关联资源

- Workspace: `d1a4dae0-18db-4e14-8d9b-f826a4c53c7e`
- Runtime: `18271ffc-a989-4b4a-8241-cc6dcd7a3e01`
- Owner: `814673bc-7841-4cf6-9af8-c81b86d9cb3f`

## 变更记录

| Date | Change |
|------|--------|
| 2026-05-22 | Initial profile created |
| 2026-05-23 | Synced profile from Multica workspace |
