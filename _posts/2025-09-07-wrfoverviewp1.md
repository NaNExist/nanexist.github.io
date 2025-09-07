---
title: "WRF Overview Part1"
date: 2025-09-07 23:17:00 +0800
categories: [WRF]
tags: [WRF,数值模式]
---

# WRF Overview Part1

这是WRF学习系列的第一期，本期将介绍WRF的模块组成和不同情况下应该运行哪些模块。

## 什么是 WRF

WRF 分为多个模块：

![](/assets/images/WRF/wrf_system_flow_chart.png)

- WRF Preprocessing System (WPS) WRF 预处理系统
- Initialization (Real and Ideal) 初始化系统
- WRF-ARW Solver (WRF) WRF-ARW 求解器
- WRF Data Assimilation (WRFDA) WRF 数据同化
- Post-processing, Analysis, and Visualization Tools 后处理，分析和可视化工具

## WPS

WPS 用于实际数据模拟。其功能包括：
1. 定义模拟区域；
2. 将陆地数据（如地形、土地利用和土壤类型）插值到模拟区域；
3. 对来自外部模型的气象输入数据进行解码和插值处理，将其转换至模拟区域。

## Initialization

WRF 模型能够同时模拟真实数据和理想数据案例。`ideal.exe` 是一个在受控环境中进行模拟的程序。理想化模拟通过包含的初始条件文件启动，该文件源自现有探空数据，并采用简化地形假设。真实数据案例则使用 WPS 的输出结果，这些输出包含源自先前运行的外部分析或预报模型（例如 GFS）生成的气象输入数据，作为 `real.exe` 程序的输入。

## WRF-ARW Solver

WRF-ARW 求解器是核心模块，我们将在后续章节详细讲述其内容。

## WRF Data Assimilation

WRF 数据同化系统（WRFDA）是一个可选程序，用于将观测数据导入由 WPS 生成的插值分析场。该系统还可通过"循环"模式运行，用于更新 WRF 模型的初始条件。

## Post-processing, Analysis, and Visualization Tools

包含了 [wrf-python](https://wrf-python.readthedocs.io/en/latest/) , [NCL](https://www.ncl.ucar.edu/) 等多种后处理程序。

## 模块使用

- 对于理想化情境运行： WRF-ARW Solver + PostProcessing
- 对于实际场景运行： WPS + WRF-ARW Solver + PostProcessing
- 对于实际场景且需要变分分析： WPS + WRFDA + WRF ARW Model + Postprocessing

本期内容到此结束。

原文来自 [WRF Users Guide documentation](https://www2.mmm.ucar.edu/wrf/users/wrf_users_guide/build/html/overview.html#wrf-arw-solver)
