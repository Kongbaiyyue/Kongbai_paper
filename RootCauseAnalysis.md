# Paper
### Bayesian
- [CloudRCA](https://dl.acm.org/doi/pdf/10.1145/3459637.3481903) ali
- [BALANCE](https://arxiv.org/pdf/2301.13572.pdf) ali

### multimodal
- [MMRCA](https://www.researchgate.net/profile/Gary-White-13/publication/357636273_MMRCA_MultiModal_Root_Cause_Analysis/links/61d771bdb6b5667157cf29c2/MMRCA-MultiModal-Root-Cause-Analysis.pdf) 

### Problem
- the value of the KPI in each dimension equals the sum of the values of its attributes (BALANCE)
- all the KPIs and their attributes can be monitored. (BALANCE)
- 评价指标：mean time to resolve(MTTR)
- rare anomaly sample

### Challenge
- Lack of labels (MMRCA)
- Efficiency and accuracy (MMRCA)

## root cause localization

### 微服务根因定位
- [MicroHECL: High-Efficient Root Cause Localization in Large-Scale Microservice Systems](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=9402058) ICSE-SEIP2021

- [AutoMap: Diagnose Your Microservice-based Web Applications Automatically](https://sci-hub.se/https://doi.org/10.1145/3366423.3380111) www2020


### SQL根因定位
- [PinSQL: Pinpoint Root Cause SQLs to Resolve Performance Issues in Cloud Databases](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=9835371) ICDE2022

- [Diagnosing Root Causes of Intermittent Slow Queriesin Cloud Databases](http://www.vldb.org/pvldb/vol13/p1176-ma.pdf) vldb2020


### (有几种模式)
### 适合哪些数据类型
### 有哪些问题



$ session_Q = \{ \sum_{q\in Q} P(observed(sel_t,q)), t \in {t_s, t_s + 1, ..., t_e} \} $

$ trend(Q) = corr(session_{Qt}, session_t; W) $ 

$ scale\_ trend(Q) = corr(\frac {session_{Qt}} {session_t}, session_t) $

$ impact(Q) = \beta \cdot trend(Q) + scale\_ trend(Q) + \alpha \cdot scale(Q)$
