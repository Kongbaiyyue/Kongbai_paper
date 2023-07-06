# [MMRCA: MultiModal Root Cause Analysis](https://www.researchgate.net/profile/Gary-White-13/publication/357636273_MMRCA_MultiModal_Root_Cause_Analysis/links/61d771bdb6b5667157cf29c2/MMRCA-MultiModal-Root-Cause-Analysis.pdf)

## challenges
- 大量的 metrics：millions
- 准确性和时间成本

## 主要方法
减少 metrics 的数量，从而达到找到根因的 metrics 、减少时间、提高MAP@5指标的目的。

## input
### MultiModal data
- key-value configurations
- graph topologies
    - dynamic, directed and weighted graph
- traces
- time series metric

topologies 和 traces 的区别：
topologies描述服务之间的连接和 服务部署在哪个节点上


## output 
a fault trigger( to  identify what was the actual root cause of this fault by leveraging topology, trace, metric and configuration data and to return the result in under 3 minutes.)

## dataset
一个可重复的真实的实验环境，可以注入错误、并将错误进行传递。并且能够已知开始的错误节点。

## Evaluation Metrics
[mAP@k](https://zhuanlan.zhihu.com/p/382401940)
 memory usage
 the scalability of the algorithm with an increasing number of metrics and services。

## model overview

### Topology Reduction
减少节点，识别偏离之前行为的节点。 
- 数据处理和特征提取：处理 traces， topology，configuration。
- topology 信息：结合traces weight 构建一个动态、有向、有权图。
- 计算图中前一个时间窗口 响应时间、响应代码、吞吐量的偏差。
- configuration 的改变会作为 weight 添加到 services 中，这个权重与偏离先前行为的 services 相结合。
- 根据 weight 选取 top-k 个服务
 
### Metric Causality
对齐采样率和开始时间不同的 metrics。
- 数据处理和特征提取：删减过的 metrics 和 configurations。
- 时间对齐：some rounding combined with the common lowest factor between data sets。
- 计算时间因果关系：transfer entropy, cosine distance and granger causality。
Granger causality was found to give the most accurate causal results, while keeping the overhead low。
- The metrics are then ranked by P-value. P-value 越低 casual relationship越大。

### Metric Reduction
删除与根因无关的指标。
- 删除多余指标：标准差判断指标是否为静态指标，KV test and auto-correlation判断指标是否随机。
- 指标聚类：差分统计(gap statistic)识别正确类别，k-means聚类。
- 根据时间序列的因果关系算法对抽样出来的类样本预测出来的P-value值判断哪个 metrics 类别最有可能包含 异常的 metrics 。

## 算法
- Granger causality test：衡量 时间变量x 与 时间变量y 的相关性，预测出来的p-value越少，越有影响。
- Dynamic Time warping（DTW）：计算两个时间序列的相似度，适用不同长度，不同节奏的时间序列。
- common lowest factor（CLF）
- 标准差：计算标准差，越大越可能是根因
-  


# GRANO: Interactive Graph-based Root Cause Analysis for Cloud-Native Distributed Data Platform

## 异常类型
- 与其他 services 上的 metric 不一致
- metric 不同于正常的模式
- metric 突变

# 可以做的点

