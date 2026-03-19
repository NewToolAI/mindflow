# 需求图 (Requirement)

## 图示说明
需求图是用于展示系统需求及其与其他元素（如组件、测试用例）关系的图示。帮助跟踪和管理系统需求。

## 适用范围
- 需求管理
- 系统架构规划
- 需求追溯
- 验收标准定义
- 合规性说明

## 语法示例

```mermaid
requirementDiagram

    requirement 测试需求1 {
        id: 1
        text: 系统应支持用户登录功能
        risk: Low
        reqSet: 功能需求
    }

    requirement 测试需求2 {
        id: 2
        text: 响应时间应小于3秒
        risk: Medium
        reqSet: 性能需求
    }

    requirement 测试需求3 {
        id: 3
        text: 系统应符合GDPR规范
        risk: High
        reqSet: 合规需求
    }

    functionalRequirement 测试需求1

    performanceRequirement 测试需求2

    complianceRequirement 测试需求3

    element 用户服务 {
        type: Software
    }

    element 数据库 {
        type: Software
    }

    userService - fulfills > 测试需求1
    database - fulfills > 测试需求1
```

## 语法说明

### 需求定义
```mermaid
requirementDiagram
    requirement 需求名称 {
        id: 编号
        text: 需求描述
        risk: 风险等级
        reqSet: 需求集合
    }
```

### 风险等级
- `Low`: 低风险
- `Medium`: 中风险
- `High`: 高风险

### 需求类型
- `requirement`: 通用需求
- `functionalRequirement`: 功能需求
- `performanceRequirement`: 性能需求
- `interfaceRequirement`: 接口需求
- `complianceRequirement`: 合规需求
- `designConstraint`: 设计约束

### 元素定义
```mermaid
requirementDiagram
    element 元素名称 {
        type: 类型
        docref: 文档引用
    }
```

### 元素类型
- `Software`: 软件组件
- `Hardware`: 硬件组件
- `Process`: 过程/流程
- `External`: 外部实体

### 关系类型
- `- fulfills >`: 满足
- `- copies >`: 复制
- `- derives >`: 派生
- `- satisfies >`: 实现
- `- verifies >`: 验证
- `- refines >`: 细化

## 配置说明

### 样式选项
可以配置不同风险等级的颜色显示。

### 注意事项
- 需求 ID 应唯一
- 合理组织需求集合
- 明确元素类型和关系
