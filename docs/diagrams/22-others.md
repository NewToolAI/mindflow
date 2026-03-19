# 其他示例 (Other Examples)

## 图示说明
本章节汇总一些不属于标准类别的特殊图示类型和使用技巧，以及 Mermaid 的高级用法。

## 语法示例

### 甘特图与里程碑

```mermaid
gantt
    title 产品发布计划
    dateFormat YYYY-MM-DD

    section 开发
    需求分析: 01, 2024-01-01, 10d
    设计阶段: 02, after 01, 7d
    开发实现: 03, after 02, 21d

    section 发布
    内部测试: 04, after 03, 7d
    Beta发布: milestone, 05, 2024-03-01, 0d
    正式发布: milestone, 06, 2024-03-15, 0d
```

### 复合流程图

```mermaid
flowchart TB
    subgraph 前端
        A[用户界面] --> B[状态管理]
    end

    subgraph 后端
        C[API网关] --> D[业务逻辑]
        D --> E[数据访问]
        E --> F[(数据库)]
    end

    A --> C
    B --> C
```

### 时序图与循环

```mermaid
sequenceDiagram
    participant C as 客户端
    participant S as 服务器

    loop 每分钟
        C->>S: 发送心跳
        S-->>C: 心跳响应
    end

    C->>S: 开始任务
    S-->>C: 任务ID
    loop 处理中
        S-->>C: 进度更新
    end
    S-->>C: 任务完成
```

### 多个图的组合展示

```mermaid
pie title 技术栈分布
    "前端": 35
    "后端": 40
    "DevOps": 15
    "其他": 10
```

## Mermaid 配置与主题

### Mermaid 主题设置

````markdown
```mermaid
%%{init: {'theme':'base', 'themeVariables': { 'primaryColor': '#ff9900'}}}%%
flowchart LR
    A --> B
```
````

### 常用主题
- `default`: 默认主题
- `base`: 基础主题
- `dark`: 暗色主题
- `forest`: 森林主题
- `neutral`: 中性主题

## Mermaid 扩展语法

### Markdown 中的 Mermaid

可以在 Markdown 文档中直接嵌入 Mermaid 图：

````markdown
这是一段文字说明。

```mermaid
sequenceDiagram
    A->>B: 消息
```
````

### Mermaid 中的 HTML

部分 Mermaid 类型支持 HTML 格式的文本：

```mermaid
pie title 示例
    "项 A": 40
    "项 B<br/>多行": 35
    "项 C": 25
```

## 常见问题与技巧

### 1. 文本换行
```mermaid
flowchart TD
    A["第一行<br/>第二行"] --> B
```

### 2. 特殊字符转义
使用引号包裹包含特殊字符的文本。

### 3. 子图引用
```mermaid
flowchart TB
    subgraph S1
        A --> B
    end
    C --> A
    S1 --> D
```

### 4. CSS 样式
```mermaid
flowchart TD
    A --> B
    style A fill:#f9f,stroke:#333,stroke-width:2px
    classDef highlight fill:#ff9
    class B highlight
```

## 参考资源

- [Mermaid 官方文档](https://mermaid.js.org/)
- [Mermaid Live Editor](https://mermaid.live/)
- [Mermaid GitHub](https://github.com/mermaid-js/mermaid)

## 注意事项

- 部分图示类型（如 C4、ZenUML、Sankey、Architecture）是实验性功能
- 实验性功能的语法可能随版本更新变化
- 建议在正式环境中使用前验证语法
- Mermaid 版本更新可能带来新的图示类型和语法
