# Kanban (看板)

## 图示说明
看板是一种可视化的工作流管理工具，通过列和卡片来展示任务的进度和状态。广泛用于敏捷开发和项目管理。

## 适用范围
- 项目任务管理
- 敏捷开发流程
- 工作流程可视化
- 团队协作展示
- 进度跟踪

## 语法示例

```mermaid
kanban
    title 项目开发看板

    [待办] --> [进行中] --> [测试] --> [完成]

    [待办]:
        - 用户故事A
        - 用户故事B
        - 缺陷修复1

    [进行中]:
        - 功能开发X
        - 性能优化Y

    [测试]:
        - 功能模块Z

    [完成]:
        - 基础架构搭建
        - 数据库设计
```

```mermaid
kanban
    title 软件发布流程

    [Backlog] --> [Sprint Planning] --> [In Progress] --> [Code Review] --> [Staging] --> [Production]

    [Backlog]:
        - 需求收集
        - 优先级排序

    [Sprint Planning]:
        - Sprint 1 规划

    [In Progress]:
        - 开发任务1
        - 开发任务2

    [Code Review]:
        - PR #123
        - PR #124

    [Staging]:
        - 发布候选版本

    [Production]:
        - v1.0.0 已发布
        - v1.0.1 已发布
```

## 语法说明

### 基本语法
```mermaid
kanban
    title 标题

    [列1] --> [列2] --> [列3]

    [列1]:
        - 任务1
        - 任务2
```

### 列定义
```mermaid
kanban
    [待办事项]
    [进行中]
    [已完成]
```

### 流程箭头
```mermaid
kanban
    [A] --> [B]
    [B] --> [C]
    [A] -.-> [D]: 快速通道
```

### 任务项
- 使用 `-` 前缀列出任务
- 可以嵌套子任务
- 支持 checkbox 格式

### 多泳道
```mermaid
kanban
    [团队A任务] & [团队B任务] --> [共同任务]
```

## 配置说明

### 样式选项
```mermaid
kanban
    title 示例

    style [进行中] fill:#fff3e0
    style [完成] fill:#e8f5e9
```

### 限制线 (WIP)
```mermaid
kanban
    [进行中]: 3
```

### 注意事项
- 任务数量适中
- 流程清晰易读
- 列名简洁明了
