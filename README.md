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
docs/theory/     符号约定、勘误与数值锚点（00-notation.md）+ 使用者手稿（01-math.md）
notebooks/       唯一维护的文档：01_quality_theory.ipynb（理论三部分）+ 00_environment_check.ipynb
src/             模拟用的可复用 Python 包（factorio_quality）
tests/           数值验证测试
```

## 工作流

1. 理论与公式的唯一维护物是 `notebooks/01_quality_theory.ipynb`（Markdown + LaTeX，三部分：基础转移矩阵 / 纯回收机 / 组装+回收机），直接在 JupyterLab 中编辑。
2. 符号约定、待确认问题与数值锚点见 `docs/theory/00-notation.md`；使用者手稿 `01-math.md` 原样保留。
3. 后续在 notebook 中加入带具体参数的模拟代码与图表，可复用逻辑放 `src/factorio_quality`，用 `ruff check .` 保证代码风格。
