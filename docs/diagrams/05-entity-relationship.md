# 实体关系图 (Entity Relationship Diagram)

## 图示说明
实体关系图用于表示数据库中的实体、它们的属性以及实体之间的关系。是数据库设计和建模的重要工具。

## 适用范围
- 数据库设计
- 数据建模
- 业务数据关系梳理
- API 数据结构设计
- 系统集成数据映射

## 语法示例

```mermaid
erDiagram
    用户 {
        int id PK
        string 用户名
        string 邮箱
        string 密码
        datetime 创建时间
    }

    订单 {
        int id PK
        int 用户_id FK
        decimal 总金额
        string 状态
        datetime 创建时间
    }

    商品 {
        int id PK
        string 名称
        string 描述
        decimal 价格
        int 库存
    }

    订单详情 {
        int 订单_id FK
        int 商品_id FK
        int 数量
        decimal 小计
    }

    用户 ||--o{ 订单 : "下订单"
    订单 ||--|{ 订单详情 : "包含"
    商品 ||--o{ 订单详情 : "被包含"
```

## 语法说明

### 基本语法
```mermaid
erDiagram
    ENTITY_NAME {
        type field_name PK "注释"
        type field_name FK "注释"
        type field_name "注释"
    }
```

### 字段类型
- `int`, `string`, `boolean`, `datetime`, `decimal`, `float`

### 字段修饰符
- `PK`: 主键 (Primary Key)
- `FK`: 外键 (Foreign Key)
- `UK`: 唯一键 (Unique Key)
- `NN`: 非空 (Not Null)

### 关系符号

| 符号 | 说明 |
|------|------|
| `||` | 恰好一个 |
| `o|` | 零或一个 |
| `}|` | 一个或多个 |
| `o{` | 零或多个 |
| `||--||` | 一对一 |
| `||--o{` | 一对多 |
| `}|--||` | 多对一 |
| `}|--o{` | 多对多 |

### 关系标签
```mermaid
erDiagram
    A ||--o{ B : "关系标签"
    A {
        int id PK
    }
    B {
        int id PK
        int a_id FK
    }
```

## 配置说明

| 配置项 | 说明 |
|--------|------|
| showEntityTypes | 显示实体类型 |
| entitySeparation | 实体间距 |
| relationshipSeparation | 关系间距 |

### 样式配置
```mermaid
erDiagram
    CUSTOMER ||--o{ ORDER : places
    CUSTOMER {
        string name "姓名"
        int cust_id PK
    }
```
