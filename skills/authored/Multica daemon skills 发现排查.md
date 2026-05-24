---
name: "Multica daemon skills 发现排查"
skill_id: "b9e68923-6264-482b-97a4-51e8398f8fe8"
description: "排查 multica daemon 无法发现环境内 skills 的复用方案"
created_at: "2026-05-20T01:04:39Z"
updated_at: "2026-05-20T01:04:39Z"
source: "multica workspace skill"
---

# Multica daemon skills 发现排查

## 结论
- `multica daemon` 当前运行环境里已经同时满足这两个条件：
  - `HERMES_HOME=/opt/data`
  - `/opt/data/.skills -> /opt/data/skills`
- 因此，本机这次问题的根因不是 `/opt/data/.skills` 缺失。
- 目前更可能的实际情况是：
  1. Hermes 本地 skills 能被 Hermes 自己看到；
  2. 但 Multica 工作区里的 `skill` 资源、以及 agent 的 `skills` 绑定，是另一套数据；
  3. daemon 不会自动把本地 Hermes skills 同步成 Multica 工作区 skills。

## 现场判断方法

### 1. 先看 daemon 进程环境
确认 daemon 进程里是否有：
- `HERMES_HOME=/opt/data`
- `HOME=/opt/data`（建议统一）

### 2. 检查技能目录映射
需要满足至少一个稳定入口：
- 主目录：`/opt/data/skills`
- 兼容别名：`/opt/data/.skills -> /opt/data/skills`

### 3. 区分两套 skill 概念
- **Hermes local skills**：Hermes CLI 通过 `hermes skills list` 看到的本地/builtin skills
- **Multica workspace skills**：`multica skill list` 返回的工作区 skill 资源

如果 `hermes skills list` 正常、但 `multica skill list` 没有对应项，说明问题不是扫描不到目录，而是没有导入到 Multica 工作区。

## 复用方案（推荐）

### 方案 A：统一 daemon 启动环境
让 daemon 固定使用同一套 home/skills 视图：
- `HOME=/opt/data`
- `HERMES_HOME=/opt/data`
- 保留 `/opt/data/.skills -> /opt/data/skills` 兼容链接

这样可以避免 daemon 和手工 shell 使用不同 home，导致看到不同 skills。

### 方案 B：把需要给 Multica agent 使用的技能显式导入工作区
不要依赖 daemon 自动扫描 Hermes 本地目录。

标准流程：
1. 先把技能作为 **Multica workspace skill** 创建/导入
2. 再用 `multica agent skills set` 显式绑定到 agent

这样最稳定，也最容易审计和迁移。

## 建议的运维约定
1. **Hermes 本地技能目录统一只认 `/opt/data/skills`**
2. **`/opt/data/.skills` 只作为兼容软链保留**
3. **daemon 启动环境固定导出 `HOME=/opt/data` 与 `HERMES_HOME=/opt/data`**
4. **凡是要在 Multica 里可见/可分配的技能，一律导入为 workspace skill，不依赖本地扫描**

## 验收标准
- `hermes skills list` 能看到本地 skills
- `multica skill list` 能看到需要给工作区使用的 skill
- `multica agent skills list <agent-id>` 能看到 agent 绑定结果
- daemon 重启后结果保持不变
