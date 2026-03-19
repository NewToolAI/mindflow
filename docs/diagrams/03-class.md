# 类图 (Class Diagram)

## 图示说明
类图是面向对象编程中用于展示类、类的属性、方法和类之间关系的图示。是 UML（统一建模语言）中最常用的图示之一。

## 适用范围
- 软件架构设计
- 代码结构说明
- 对象关系建模
- API 接口设计
- 数据库表结构设计

## 语法示例

```mermaid
classDiagram
    class Animal {
        +String name
        +int age
        +makeSound() void
        +eat() void
    }

    class Dog {
        +String breed
        +bark() void
        +fetch() void
    }

    class Cat {
        +boolean isIndoor
        +meow() void
        +scratch() void
    }

    Animal <|-- Dog : 继承
    Animal <|-- Cat : 继承
    Dog ..> Animal : 依赖
```

```mermaid
classDiagram
    class UserService {
        -UserRepository userRepo
        +createUser(name: String) User
        +deleteUser(id: Long) boolean
        +findUserById(id: Long) User
    }

    class UserRepository {
        +save(User) User
        +findById(Long) User
        +findAll() List~User~
        +deleteById(Long) void
    }

    UserService o-- UserRepository : 聚合
```

## 语法说明

### 类声明
```mermaid
classDiagram
    class ClassName {
        +publicField String
        -privateField int
        #protectedField boolean
        ~packageField double
        +publicMethod() void
        -privateMethod() int
    }
```

### 访问修饰符
- `+`: public（公有）
- `-`: private（私有）
- `#`: protected（受保护）
- `~`: package（包级别）

### 关系类型
- `<|--`: 继承（泛化）
- `*--`: 组合
- `o--`: 聚合
- `-->`: 关联
- `..>`: 依赖
- `..|>`: 实现（接口）

### 关系标签
```mermaid
classDiagram
    A "1" *-- "many" B : 组合关系
    C "1" --> "1" D : 一对一
```

### 接口和抽象类
```mermaid
classDiagram
    interface Printable {
        <<interface>>
        +print() void
    }

    class Document {
        <<abstract>>
        +print() void
    }

    Document ..|> Printable : 实现
```

### 类注解
```mermaid
classDiagram
    class Singleton {
        <<Singleton>>
        -static instance: Singleton
        -Singleton()
        +getInstance(): Singleton
    }
```

## 配置说明

| 配置项 | 说明 |
|--------|------|
| showClassMembers | 显示类成员 |
| defaultMemberAlignment | 成员对齐方式 |
| nodeSpacing | 节点间距 |
| rankSpacing | 层级间距 |

### 关系样式
```mermaid
classDiagram
    style A fill:#f9f,stroke:#333,stroke-width:2px
```
