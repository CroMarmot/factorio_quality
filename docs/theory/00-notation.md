# 记号约定与勘误笔记

本项目**唯一维护的理论文档是 `notebooks/01_quality_theory.ipynb`**（三章：基础转移矩阵 / 纯回收机循环 / 组装机+回收机循环）。符号、定义与推导以 notebook 为准。本文件只存放正文之外的规范性笔记：待确认问题与勘误、数值备注、资料来源。`01-math.md` 为使用者手稿（保留原样）。

## 已确认勘误

1. **$400\%$ 的表述**（已确认）：wiki “趋近 $400\%$ 收敛变慢”指总产能**倍率** $1+P$，不是产能加成 $P$。收敛条件为 $(1+P)\cdot\tfrac14 < 1$，即 $1+P < 400\%$（等价于 $P < 300\%$）。notebook “产能加成上限约 $300\%$”的表述与此一致，无误。

## 待确认问题与勘误清单

1. **收集范围**：主线只收集传奇产品、不收集材料。此前参考的网页与 wiki 示例同时移出了传奇材料，但实际的代数公式与矩阵形式以**只收集产品**为准（收集材料只是另一个变体，notebook 未展开）。

## 数值备注

- 收敛临界：$(1+P)\cdot\tfrac14 < 1$，即 $1+P < 400\%$（$P < 300\%$）时收敛；逼近临界时变慢，超过后发散。（已记录，暂不展开讨论。）

## 资料来源

- Factorio wiki: Quality（升级规则表、$10\times10$ 转移矩阵示例、$400\%$ 产能收敛表述）：https://wiki.factorio.com/Quality/zh
- dfamonteiro: [factorio-quality-1](https://dfamonteiro.com/posts/factorio-quality-1/)、[factorio-pure-recycler-loop](https://dfamonteiro.com/posts/factorio-pure-recycler-loop/)、[factorio-recycler-assembler-loop](https://dfamonteiro.com/posts/factorio-recycler-assembler-loop/)、[factorio-asteroid-chunk-recycling](https://dfamonteiro.com/posts/factorio-asteroid-chunk-recycling/)。
- 使用者手稿：`01-math.md`。
