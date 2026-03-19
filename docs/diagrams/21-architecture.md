# 架构图 (Architecture)

## 图示说明
架构图用于展示软件系统或技术架构的组件、连接和依赖关系。是系统设计和文档化的重要工具。

## 适用范围
- 系统架构设计
- 技术栈展示
- 云架构可视化
- 微服务架构
- 基础设施架构

## 语法示例

```mermaid
architecture-beta

   group api[API层]
        service apiserver[API Server]::cloud
        service gateway[API Gateway]::cloud
    end

    group application[应用层]
        service frontend[前端应用]::web
        service backend[后端服务]::app
        service worker[后台任务]::app
    end

    group data[数据层]
        database db[(数据库)]
        cache redis[缓存]
        queue queue[消息队列]
    end

    api.apiserver --> application.backend
    api.gateway --> application.frontend
    application.backend --> data.db
    application.backend --> data.cache
    application.worker --> data.queue
    data.queue --> application.backend
```

```mermaid
architecture-beta

    service internet[互联网]:::public
    service cdn[CDN]:::cloud
    service lb[负载均衡]:::infrastructure
    service web1[Web服务器1]:::web
    service web2[Web服务器2]:::web
    service app1[应用服务器1]:::app
    service app2[应用服务器2]:::app
    service db[主数据库]:::database
    service dbreplica[从数据库]:::database

    internet --> cdn
    cdn --> lb
    lb --> web1
    lb --> web2
    web1 --> app1
    web2 --> app2
    app1 --> db
    app2 --> dbreplica
    app1 --> app2
```

## 语法说明

### 基本语法
```mermaid
architecture-beta

    group 组名称[组标签]
        service 服务名[服务标签]::类型
    end

    服务A --> 服务B
```

### 服务定义
```mermaid
architecture-beta
    service name[显示名称]::类型
```

### 服务类型
- `cloud`: 云服务
- `web`: Web 服务
- `app`: 应用程序
- `database`: 数据库
- `infrastructure`: 基础设施
- `external`: 外部服务

### 组定义
```mermaid
architecture-beta
    group 组名[显示名称]
        ...
    end
```

### 连接关系
```mermaid
architecture-beta
    service a[...]:::type
    service b[...]:::type

    a --> b: 连接说明
```

### 样式类
```mermaid
architecture-beta
    service s[...]:::type

    classDef custom fill:#f9f,stroke:#333
    class s custom
```

## 配置说明

### 布局选项
```mermaid
architecture-beta
    config
        showShadows true
```

### 注意事项
- Architecture 是 beta 功能
- 语法可能随版本更新变化
- 建议查看官方文档确认最新语法
