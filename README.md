# Soybean Data Analyzer (SDA) 文档

## 1. 工具简介

Soybean Data Analyzer (SDA) 是一个专业的大豆数据统计分析工具，旨在为研究人员提供高效、专业的数据处理和分析能力。

### 主要功能
- 自动数据读取与清洗
- 全面的统计分析（描述性统计、假设检验、相关性分析）
- 出版物质量的图表生成
- 自动报告生成（Markdown 和 HTML 格式）
- 标准化的输出文件夹结构

## 2. 系统要求

### 硬件要求
- CPU: 至少 2 核心
- 内存: 至少 4GB
- 存储空间: 至少 1GB 可用空间

### 软件要求
- Python 3.8 或更高版本
- 依赖库：pandas, numpy, matplotlib, seaborn, scipy, statsmodels, jinja2, markdown

## 3. 安装指南

### 步骤 1: 克隆或下载代码

### 步骤 2: 安装依赖
```bash
pip install -r requirements.txt
```

## 4. 使用方法

### 命令行接口

**基本用法：**
```bash
python sda.py --input <数据文件路径> [选项]
```

**参数说明：**
- `--input, -i`: 输入数据文件路径（支持 TXT、CSV、Excel 格式）
- `--output, -o`: 输出文件夹路径（默认: analysis_results）
- `--analysis, -a`: 分析类型（默认: comprehensive）
  - `comprehensive`: 综合分析（所有分析）
  - `categorical`: 分类变量分析
  - `quantitative`: 数量变量分析
  - `correlation`: 相关性分析
- `--verbose, -v`: 详细输出模式
- `--version`: 显示版本信息

**示例：**
```bash
# 基本分析
python sda.py --input "黑农大豆表型数据2025.txt"

# 指定输出目录
python sda.py --input "数据.csv" --output "分析结果"

# 仅进行相关性分析
python sda.py --input "数据.xlsx" --analysis correlation

# 详细模式
python sda.py --input "数据.txt" --verbose
```

### 程序接口

```python
from sda import SoybeanDataAnalyzer

# 初始化分析器
analyzer = SoybeanDataAnalyzer(
    input_file="黑农大豆表型数据2025.txt",
    output_dir="分析结果",
    analysis_type="comprehensive",
    verbose=True
)

# 运行分析
analyzer.run()
```

## 5. 输出结果

### 文件夹结构
```
分析结果/
└── analysis_20260322_123456/  # 时间戳目录
    ├── data/                  # 数据文件
    │   ├── raw_data.csv       # 原始数据
    │   └── processed_data.csv # 处理后数据
    ├── figures/               # 图表
    │   ├── png/               # PNG 格式图表
    │   ├── pdf/               # PDF 格式图表
    │   └── tiff/              # TIFF 格式图表
    ├── tables/                # 表格数据
    ├── reports/               # 报告
    │   ├── report.md          # Markdown 报告
    │   └── report.html        # HTML 报告
    └── logs/                  # 日志文件
```

### 报告内容
- 数据概况
- 描述性统计
- 分类变量分析
- 数量变量分析
- 相关性分析
- 图表分析
- 结论与建议

## 6. 数据格式要求

### 支持的文件格式
- 文本文件（.txt）：使用逗号或制表符分隔
- CSV 文件（.csv）
- Excel 文件（.xlsx, .xls）

### 数据结构
- 第一行为列名
- 分类变量建议使用数字编码或文本标签
- 数量变量应为数值型

## 7. 常见问题

### Q: 数据读取失败
**A:** 检查文件路径是否正确，文件编码是否为 UTF-8，文件格式是否符合要求。

### Q: 图表中文显示乱码
**A:** 工具已内置中文支持，会自动使用系统中可用的中文字体。

### Q: 分析结果不符合预期
**A:** 检查数据质量，确保数据类型正确，避免缺失值和异常值。

### Q: 内存不足
**A:** 对于大型数据集，建议增加系统内存或分批处理数据。

## 8. 故障排除

### 日志文件
工具会在 `logs` 目录生成详细的日志文件，可用于排查问题。

### 错误信息
- `FileNotFoundError`: 检查文件路径是否正确
- `ValueError`: 检查数据格式是否正确
- `MemoryError`: 增加内存或减少数据量

## 9. 扩展与定制

### 配置文件
可通过修改 `config/settings.py` 来调整分析参数和可视化样式。

### 自定义图表
可在 `visualization/plotter.py` 中添加自定义图表类型。

### 扩展分析方法
可在 `analysis` 目录中添加新的分析模块。

## 10. 示例

### 示例 1: 基本分析
```bash
python sda.py --input "黑农大豆表型数据2025.txt"
```

### 示例 2: 仅分析分类变量
```bash
python sda.py --input "数据.csv" --analysis categorical
```

### 示例 3: 详细模式分析
```bash
python sda.py --input "数据.xlsx" --verbose
```

## 11. 版本历史

- **v1.0.0** (2026-03-22)
  - 初始版本
  - 支持基本的统计分析和图表生成
  - 自动报告生成功能

## 12. 联系与支持

如有问题或建议，请联系：
- 邮箱: support@soybean-analyzer.com
- 网站: https://soybean-analyzer.com

---

*本工具由 Soybean Data Analyzer 开发团队维护*