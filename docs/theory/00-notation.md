# 记号约定与勘误笔记

本项目**唯一维护的理论文档是 `notebooks/01_quality_theory.ipynb`**（三章：基础转移矩阵 / 纯回收机循环 / 组装机+回收机循环）。符号、定义与推导以 notebook 为准。本文件只存放正文之外的规范性笔记：待确认问题与勘误、待验证的数值锚点、资料来源。`01-math.md` 为使用者手稿（保留原样）。

## 待确认问题与勘误清单

1. **$400\%$ 的表述**：wiki “趋近 $400\%$ 收敛变慢”若指总产能**倍率** $1+P\to 4$，则 notebook 的“产能加成上限约 $300\%$”与之一致；若指产能**加成**，则需改写为 $P<400\%$。请确认。
2. **收集范围**：主线只收集传奇产品、不收集材料。此前参考的网页与 wiki 示例同时移出了传奇材料，但实际的代数公式与矩阵形式以**只收集产品**为准（收集材料只是另一个变体，notebook 未展开）。

## 待验证的数值锚点（模拟代码回归目标）

- 纯回收机、回收机品质概率 $q = 10\%$：传奇占比 $0.00693\%$，即约 $14430 : 1$ 的进料比。
- 纯回收机、回收机品质概率 $q = 24.8\%$（$4\times6.2\%$）：传奇占比 $0.03667\%$，即约 $2726.9 : 1$。
- wiki 组装+回收示例（$q=25\%$、产能总量 $50\%$）：稳态行向量 $[\,1.267,\ 0.203,\ 0.083,\ 0.0297,\ 0.0063 \mid 1.426,\ 0.656,\ 0.205,\ 0.073,\ 0.02497\,]$，即一组原料约产出 $2.497\%$ 的传奇产品。
- 收敛临界：总产能倍率逼近 $400\%$（$P \to 300\%$）时收敛变慢；超过后发散。

## 资料来源

- Factorio wiki: Quality（升级规则表、$10\times10$ 转移矩阵示例、$400\%$ 产能收敛表述）：https://wiki.factorio.com/Quality/zh
- dfamonteiro: [factorio-quality-1](https://dfamonteiro.com/posts/factorio-quality-1/)、[factorio-pure-recycler-loop](https://dfamonteiro.com/posts/factorio-pure-recycler-loop/)、[factorio-recycler-assembler-loop](https://dfamonteiro.com/posts/factorio-recycler-assembler-loop/)、[factorio-asteroid-chunk-recycling](https://dfamonteiro.com/posts/factorio-asteroid-chunk-recycling/)。
- 使用者手稿：`01-math.md`。
