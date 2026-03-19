# 甘特图 (Gantt)

## 图示说明
甘特图是一种条形图，用于展示项目进度、时间安排和任务依赖关系。横轴表示时间，纵轴表示任务或项目组成部分。

## 适用范围
- 项目管理进度展示
- 任务时间规划
- 资源调配可视化
- 里程碑追踪
- 生产计划排程

## 语法示例

```mermaid
gantt
    title 项目开发计划
    dateFormat YYYY-MM-DD
    section 设计阶段
        需求分析: a1, 2024-01-01, 7d
        原型设计: a2, after a1, 5d
        UI设计: a3, after a2, 5d
    section 开发阶段
        前端开发: b1, after a3, 10d
        后端开发: b2, after a3, 12d
        API对接: b3, after b1, 3d
    section 测试阶段
        单元测试: c1, after b1, 5d
        集成测试: c2, after b2, 4d
        上线部署: c3, after c1 c2, 2d
```

```mermaid
gantt
    title 里程碑示例
    dateFormat YYYY-MM-DD

    section 项目阶段
    启动会议: milestone0, 2024-01-01, 0d
    需求完成: milestone1, 2024-01-15, 0d
    开发完成: milestone2, 2024-02-15, 0d
    测试完成: milestone3, 2024-03-01, 0d
    上线发布: milestone4, 2024-03-15, 0d
```

## 语法说明

### 基本语法
```mermaid
gantt
    title 标题
    dateFormat 日期格式
    section 分组名称
        任务名称: 任务ID, 开始日期, 持续时间
```

### 日期格式
- `YYYY-MM-DD`: 2024-01-15
- `YYYY-MM-DD HH:mm`: 2024-01-15 09:00
- `DD/MM/YYYY`: 15/01/2024
- `MM-DD`: 01-15（当年）

### 持续时间表示
- `7d`: 7天
- `3w`: 3周
- `2m`: 2个月
- `10h`: 10小时
- `30m`: 30分钟

### 任务依赖
```mermaid
gantt
    task1: t1, 2024-01-01, 5d
    task2: t2, after t1, 3d
    task3: t3, after t2, 2d
```

### 关键任务和里程碑
```mermaid
gantt
    完成任务: done, t1, 2024-01-01, 10d
    进行中任务: active, t2, 2024-01-05, 5d
    未来任务: t3, 2024-01-10, 3d
    里程碑: milestone, m1, 2024-01-15, 0d
```

### 任务状态
- `done`: 已完成（深色）
- `active`: 进行中（彩色）
- `crit`: 关键任务（红色边框）
- 默认: 未来任务（浅色）

## 配置说明

| 配置项 | 说明 |
|--------|------|
| title | 图表标题 |
| dateFormat | 日期格式 |
| axisFormat | 时间轴格式 |
| sectionSeparator | 分组分隔符 |
| inclusiveEndDates | 结束日期包含性 |

### 时间轴格式
```mermaid
gantt
    dateFormat YYYY-MM-DD
    axisFormat %m/%d
```
