---
name: academic-figure-gen
slug: academic-figure-gen
version: 1.0.0
displayName: 学术配图生成工作流
summary: 基于Graphviz DOT引擎的学术论文配图生成工具，支持5类图表模板、3套学术配色方案及DOCX联动输出。
description: |
  ## 学术配图生成工作流 (Academic Figure Generation Workflow)
  
  基于 Graphviz DOT 引擎，专为学术论文设计的配图生成工具。提供 5 类论文常用图表模板（架构分层图、业务流程图、工序追溯图、技术演进路线图、数据流图），3 套审稿安全配色方案（学术深蓝、色盲友好、灰阶打印安全），并支持与 python-docx 联动将生成的 PNG 图片规范插入 Word 文档。
  
  A Graphviz DOT engine-powered figure generation toolkit tailored for academic papers. Offers 5 common chart templates (architecture layered diagram, business process flow, process traceability, technology evolution roadmap, data flow diagram), 3 publication-safe color schemes (academic blue, colorblind-friendly, grayscale print-safe), and seamless DOCX integration for inserting generated PNG figures into Word documents.
  
  **触发词 / Triggers:** 学术配图、论文图表、生成图表、DOT图、架构图、流程图、追溯图、演进路线图、数据流图、academic figure、generate diagram、Graphviz DOT、论文插图、图题编号、插入Word图片、配图着色
---

# 学术配图生成工作流 (Academic Figure Generation Workflow)

## 技能概述

本技能为学术论文写作中的配图需求提供端到端解决方案：从图表设计（DOT 源码模板）→ 渲染导出（Graphviz 引擎）→ 论文插入（python-docx 联动），全流程覆盖。所有模板均使用 `{{PLACEHOLDER}}` 占位符标记可替换内容，配色方案均经过审稿安全验证（色盲友好、灰阶打印兼容）。

## 快速导航

| 文档 | 内容 |
|------|------|
| [graphviz-setup.md](references/graphviz-setup.md) | Graphviz 跨平台安装与配置 |
| [dot-templates.md](references/dot-templates.md) | 5 类图表 DOT 源码模板 |
| [color-schemes.md](references/color-schemes.md) | 3 套学术审稿安全配色方案 |
| [docx-integration.md](references/docx-integration.md) | Python 插入图片到 Word + 图题编号 |

## 图表模板索引

| 编号 | 模板名称 | 典型用途 | 关键 DOT 特征 |
|------|----------|----------|---------------|
| 1 | 架构分层图 | 系统架构、网络分层 | `rankdir=TB`, 子图分组, 层叠矩形 |
| 2 | 业务流程图 | 审批流程、操作步骤 | `rankdir=LR`, 菱形判断节点, 分支路径 |
| 3 | 工序追溯图 | 制造追溯、质量链 | 链式节点 + 扫码标识 + 数据记录 |
| 4 | 技术演进路线图 | 技术发展、版本迭代 | 水平时间轴, 阶段箭头, 里程碑标记 |
| 5 | 数据流图 | 系统交互、接口设计 | `rankdir=LR`, 圆柱数据存储, 多系统节点 |

## 触发词

中文：学术配图、论文图表、生成图表、DOT图、架构图、流程图、追溯图、演进路线图、数据流图、论文插图、图题编号、配图着色

English：academic figure, generate diagram, Graphviz DOT, paper illustration, architecture diagram, process flow, traceability chart, roadmap, data flow diagram, figure caption

## 与 DOCX 工具包联动

本技能生成的 PNG 图片可通过 [docx-integration.md](references/docx-integration.md) 中描述的 Python 脚本插入到 Word 文档中，支持：

- 图片宽度自动设为学术论文标准（11 cm 居中）
- 图题自动居中、宋体 10.5pt、编号自动重排
- 逆向插入法防止图片索引漂移
- 与 `docx` 技能或 `Word / DOCX` 技能协作完成最终排版

## 工作流快速入门

```
1. 选择模板 → 在 dot-templates.md 中选择匹配的图表类型
2. 替换占位符 → 将 {{PLACEHOLDER}} 替换为实际内容（注意隐私：使用通用化描述）
3. 选择配色 → 从 color-schemes.md 中选择一套配色方案
4. 渲染导出 → dot -Tpng input.dot -o output.png
5. 插入文档 → 使用 docx-integration.md 中的脚本插入 Word
```
