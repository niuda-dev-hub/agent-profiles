# 维护规范

本仓库用于维护 Multica 工作空间内 Agent 的人事档案。目标是：**单一信息源、低重复维护、便于人工阅读，也便于后续自动化处理。**

## 1. 维护原则

1. **以 `profiles/` 目录为唯一索引来源**  
   不在 README 手工维护 Agent 清单、状态表或模型列表；需要查看成员时，直接以目录内容为准。
2. **一位 Agent 一份主档案**  
   每个 Agent 只保留一个正式档案文件，避免拆分成多份说明文档。
3. **模板先行**  
   新建档案时先复制 `profiles/_template.md`，再填写具体内容，避免字段漂移。
4. **改动即更新**  
   当 Agent 的名称、模型、状态、能力描述或关联资源发生变化时，同步更新对应档案。

## 2. 目录与命名约定

```text
profiles/
├── _template.md
└── <Agent名称>.md
```

- 正式档案文件命名格式：`<Agent名称>.md`
- 文件名应与 frontmatter 中的 `name` 字段一致
- 使用 Agent 展示名称命名，优先保持中文名或现有对外名称
- 不要在 `profiles/` 下增加 README 副本、状态汇总表等重复索引文件

## 3. Frontmatter 字段约定

所有正式档案应保留以下字段：

- `name`: Agent 展示名称
- `agent_id`: Agent 唯一 ID
- `description`: 一句话说明用途
- `model`: 使用的模型标识
- `status`: 当前状态
- `visibility`: 可见范围
- `created_at`: 创建时间（RFC3339）
- `updated_at`: 最近更新时间（RFC3339）
- `skills`: 技能列表
- `runtime_mode`: 运行模式
- `max_concurrent_tasks`: 并发任务上限

### `status` 建议枚举

- `idle`: 空闲
- `working`: 工作中
- `blocked`: 阻塞中
- `archived`: 已归档 / 已退役

如无特殊需要，不新增自定义状态值。

## 4. 新增 Agent 档案

1. 复制模板
2. 将文件重命名为 `<Agent名称>.md`
3. 填写 frontmatter 与正文
4. 确认 `name` 与文件名一致
5. 提交变更

示例：

```bash
cp profiles/_template.md profiles/新Agent名称.md
```

## 5. 更新已有档案

以下信息变化时，应同步更新对应档案：

- 模型变更
- 状态变更
- 运行时 / workspace 关联资源变更
- 能力描述发生明显变化
- 技能配置发生变化

更新时至少检查：

- `updated_at` 是否已刷新
- 基本信息表是否与 frontmatter 一致
- 变更记录（Changelog）是否补充了关键调整

## 6. Agent 退役与归档

Agent 不再使用时：

- 保留原档案，不直接删除
- 将 `status` 标记为 `archived`
- 在正文或变更记录中注明归档时间与原因（如有）

这样可以保留工作空间内 Agent 的历史记录。

## 7. README 的职责边界

README 只负责：

- 说明仓库用途
- 解释目录结构
- 说明如何找到档案
- 链接到维护规范

README 不负责：

- 维护 Agent 名单
- 维护状态表
- 维护模型汇总
- 维护与 `profiles/` 重复的索引信息

## 8. 变更建议

如果后续 Agent 数量继续增长，优先考虑：

- 基于 `profiles/` 自动生成索引页
- 增加简单校验脚本，检查文件名、`name`、`updated_at` 等字段一致性

在没有自动化之前，保持结构简单比增加手工汇总页更重要。
