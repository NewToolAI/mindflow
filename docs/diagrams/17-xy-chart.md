# XY 图表 (XY Chart)

## 图示说明
XY 图表是一种用于展示两个变量之间关系的图表类型，支持折线图、散点图等多种形式。适合数据分析和趋势展示。

## 适用范围
- 数据趋势分析
- 变量相关性展示
- 业务数据可视化
- 科学实验结果
- 统计数据分析

## 语法示例

```mermaid
xychart-beta
    title 销售额趋势
    x-axis [1月, 2月, 3月, 4月, 5月, 6月]
    y-axis 销售额(万) 0 --> 100
    line [25, 45, 35, 65, 70, 85]
```

```mermaid
xychart-beta
    title 身高体重分布
    x-axis 体重(kg) [40, 50, 60, 70, 80, 90]
    y-axis 身高(cm) [150, 160, 170, 180, 190]
    scatter [65, 170], [70, 175], [55, 160], [80, 180]
```

## 语法说明

### 基本语法
```mermaid
xychart-beta
    title 图表标题
    x-axis X轴标签 [值1, 值2, 值3]
    y-axis Y轴标签 最小值 --> 最大值
    line [数据点1, 数据点2, 数据点3]
```

### 图表类型
- `line`: 折线图
- `bar`: 柱状图
- `scatter`: 散点图

### 数据格式
```mermaid
xychart-beta
    x-axis [类别1, 类别2, 类别3]
    y-axis 数值 0 --> 100

    line [数据1, 数据2, 数据3]
    bar [数据1, 数据2, 数据3]
```

### 多系列数据
```mermaid
xychart-beta
    title 多系列对比
    x-axis [Q1, Q2, Q3, Q4]
    y-axis 销售额(万) 0 --> 200

    line 系列A [45, 65, 85, 95]
    line 系列B [35, 55, 75, 90]
```

## 配置说明

### 轴配置
```mermaid
xychart-beta
    x-axis [A, B, C, D]
    y-axis 数值 -50 --> 150
```

### 主题样式
可以配合 Mermaid 主题设置颜色方案。

### 注意事项
- XY Chart 是 beta 功能
- 数据点数量适中
- 合理设置轴的范围
- 建议验证最新语法支持
