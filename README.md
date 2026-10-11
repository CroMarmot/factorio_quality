# Factorio 品质（Quality）理论文档与模拟

基于 Jupyter Notebook 的品质机制理论文档：Markdown + LaTeX 数学公式 + 可执行模拟代码 + 图表。

## 环境

- Python 3.13（uv 管理）

```powershell
uv sync --extra notebook        # 创建 .venv 并安装依赖
uv run jupyter lab notebooks    # 启动 JupyterLab
```

## 目录结构

```
docs/theory/     符号约定、勘误与数值锚点（00-notation.md）+ 使用者手稿（01-math.md）
notebooks/       唯一维护的文档：01_quality_theory.ipynb（理论 + 代码实现 + 常见疑问）+ 00_environment_check.ipynb
```

## 工作流

1. 理论与公式的唯一维护物是 `notebooks/01_quality_theory.ipynb`（Markdown + LaTeX + 代码，章节：基础转移矩阵 / 纯回收机 / 组装+回收机 / 代码实现与常见计算 / 常见疑问），直接在 JupyterLab 中编辑。
2. 符号约定、待确认问题与数值锚点见 `docs/theory/00-notation.md`；使用者手稿 `01-math.md` 原样保留。运行输出保留在 notebook 单元格内（不再单独生成输出文档）。
3. 模拟代码（numpy）全部在 notebook 内，无独立包；用 `ruff check .` 检查仓库内脚本风格。
