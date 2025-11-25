# LimitUp Tracker

## 项目简介
LimitUp Tracker 是一个用于获取每日股票涨停数据、统计关键指标，并将数据保存到 Excel 的 Python 工具。  
适合个人或小型量化分析、股票研究等用途。

## 功能
1. **获取涨停数据**  
   - 使用 `akshare` 接口获取东方财富涨停池数据  
   - 自动计算流通市值（单位：亿）  
   - 添加日期标记  

2. **统计每日指标**  
   - 总涨停家数  
   - 连板家数及首板数量  
   - 最高板高度  
   - 主流板块及板块对应涨停数量  
   - 平均和中位流通市值  

3. **Excel 输出**  
   - 自动生成或追加到指定目录的 Excel 文件  
   - Sheet 包含:
     - `LimitUp_Detail` : 每日涨停明细  
     - `Daily_Summary` : 每日汇总统计  

## 文件结构
```

limitup_tracker/
├── limitup_tracker.py       # 主脚本
└── limitup_tracker/         # 导出 Excel 文件的根目录

````

## 安装依赖
```bash
pip install akshare pandas openpyxl
````

## 使用方法

1. 下载脚本 `limitup_tracker.py`
2. 确保已安装依赖库
3. 运行脚本：

```bash
python limitup_tracker.py
```

4. Excel 文件将生成在 `./limitup_tracker/` 目录下，文件名格式为 `limitup_tracker_YYYYMMDD.xlsx`

## 配置说明

* **FILE_BASE**: 文件名基础
* **EXPORT_DIR**: Excel 文件导出目录
* **DETAIL_SHEET**: 涨停明细 Sheet 名称
* **SUMMARY_SHEET**: 每日汇总 Sheet 名称

## 数据来源

* 东方财富涨停池接口，由 `akshare` 提供

## 注意事项

* 如果没有涨停数据，脚本会提示“今日无涨停数据或获取失败”
* 每日数据会按日期生成单独 Excel 文件，避免覆盖历史数据

## 作者

* Jason Zhao
* 日期: 2025-11-25