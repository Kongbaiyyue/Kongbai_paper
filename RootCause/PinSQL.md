# [PinSQL: Pinpoint Root Cause SQLs to Resolve Performance Issues in Cloud Databases](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=9835371)

## concept
- Pinpointing Root Cause SQLs is ranking problem
- 只考虑active session上运行SQL数量作为指标（performance metrics） 作为数据库实例上的指标
- template(SQL) logs: SQL statement(based); related tables(based); response time(metric); number of examined rows(metric); timestamp.

## challenge
- How to effectively obtain the individual active  session of templates without degrading the database instance  performance?
- How to correctly model the impact of SQL templates on the instance active session?
- How to distinguish R-SQLs from massive SQLs through the located H-SQLs?

## related work
- classification：divide the causes into a limited collection of types.
- Top-SQL-based：select the highest SQLs via sorting performance metrics.
- Autoregressive-based：analyze causal dependency between variables on multivariate time-series data.

## step-by-step
### data collection and pre-processing
#### data
- metrices
- query logs
- propagation chain of SQLs
### anomaly detection
时序数据检测异常，检测的是数据库实例(instance)的异常
anomaly propagation chain
自定义异常（根据用户自定义的异常指标检测异常）
### root cause analysis

### repairing actions

## trick
- Considering various types of SQLs, we usually aggregate SQL queries into different SQL templates 


## 名词解释
### templates

### action session
session与数据库链接指的是同一个事情，session表示用户和instance的通信。
active session metric是一个时间点SQL query的数量
individual active session 是一个时间点，一个SQL模板Q 在active session中有多少个属于该模板Q的SQL被执行

### instance
等同于一个数据库，docker 的一个镜像。

### anomaly propagation chain
R-SQLs -> H-SQLs -> active session


## 根因类型
- 坏SQL
- 工作负载突变

## 根因分析类型
- 分类（受已知类别的根因类别限制，在复杂场景不适用）
- 聚类

