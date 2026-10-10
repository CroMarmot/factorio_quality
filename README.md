# Factorio 品质（Quality）理论文档与模拟

基于 Jupyter Notebook 的品质机制理论文档：Markdown + LaTeX 数学公式 + 可执行模拟代码 + 图表。

## 环境

- Python 3.13（uv 管理）
- 构建后端：hatchling，可选使用 hatch 运行环境脚本

```powershell
uv sync --extra notebook        # 创建 .venv 并安装依赖
uv run jupyter lab notebooks    # 启动 JupyterLab
```

使用 hatch 的等价方式（可选）：

```powershell
uvx hatch run note:lab
```

## 目录结构

```
docs/theory/     纯理论 Markdown（无代码），含 LaTeX 公式
notebooks/       混排文档：理论 + 代码 + 运行结果
src/             模拟用的可复用 Python 包
tests/           数值验证测试
scripts/         笔记本批量执行等辅助脚本
```

## 工作流

1. `docs/theory/*.md` 中沉淀非参数化的基础理论（可由 jupytext 转入 notebook）。
2. `notebooks/*.ipynb` 中给出带具体参数的模拟、折线图/散点图与具体数值。
3. `pytest` + `ruff check .` 保证数值与代码正确。
