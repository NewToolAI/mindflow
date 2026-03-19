# 数据包图 (Packet)

## 图示说明
数据包图用于展示网络数据包的结构或协议数据单元（PDU）的组成。适合网络协议学习和通信架构说明。

## 适用范围
- 网络协议教学
- 数据结构展示
- 通信协议说明
- 数据封装解析
- OSI 模型可视化

## 语法示例

```mermaid
packet
    title 数据包结构示例

    0-15: 源端口 (Source Port)
    16-31: 目标端口 (Destination Port)
    32-63: 序列号 (Sequence Number)
    64-95: 确认号 (Acknowledgment Number)
    96-99: 数据偏移|保留|控制标志
    100-111: 窗口大小 (Window Size)
    112-127: 校验和 (Checksum)
    128-143: 紧急指针 (Urgent Pointer)
    144-159: 选项 (Options)
    160-191: 数据 (Data)
```

```mermaid
packet
    title IPv4 数据包头部

    0-3: 版本 (4位)
    4-7: 头部长度 (4位)
    8-15: 服务类型 (TOS)
    16-31: 总长度 (Total Length)
    32-47: 标识 (Identification)
    48-50: 标志 (Flags)
    51-63: 片偏移 (Fragment Offset)
    64-71: 生存时间 (TTL)
    72-79: 协议 (Protocol)
    80-95: 头部校验和 (Header Checksum)
    96-127: 源IP地址
    128-159: 目标IP地址
    160-191: 选项 (可选)
```

## 语法说明

### 基本语法
```mermaid
packet
    title 标题

    起始-结束: 字段名 (可选说明)
    起始-结束: 字段名
```

### 字段格式
- `起始-结束`: 比特位置（0-indexed）
- 可以包含括号内的说明文字
- 每行一个字段

### 颜色标记
```mermaid
packet
    0-7: 头部
    8-31: 数据

    style 0-7 fill:#f96
```

### 分组显示
```mermaid
packet
    title 分组示例

    0-3: 组1
    4-7: 组2
    0-7: 整体覆盖
```

## 配置说明

### 宽度设置
```mermaid
packet
    title 示例
    0-15: 字段1
        0-7: 子字段1a
        8-15: 子字段1b
```

### 样式配置
```mermaid
packet
    0-31: 数据

    style 0-31 fill:#e1f5fe
```

### 注意事项
- 位置范围应正确
- 避免重叠
- 字段名称应清晰
