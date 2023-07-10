## challenge
- inaccurate detection of service anomalies.
- inefficient traversing of service dependency graph.

## types of service anomalies 
- performance  (anomalous increase of response time (RT)).
- reliability
- traffic

### anomaly detection
- The 3-sigma rule states

## evaluation
- top-3 hit radio

## step-by-step
- 构建图: 发现异常时的前 60min 发生的服务调用
- 异常传播链路分析: 抽取候选根因
- 异常分数排序: Pearson correlation coefficient方法进行相关性排序，排序指标是看初始异常指标和候选异常指标趋势的相关性

### 异常传播链路分析
- 分析过程
    - 入口节点分析：
    - 异常传播链路扩展：检测上游和下游节点中的异常节点，知道最终节点为止。
    - 候选根因：终点的异常节点为异常候选节点。
- 异常检测
    - 使用OC-SVM比聚类方法的优势是：
        - 建模简单
        - 可解释性强
        - 更好的泛化能力

    - 模型特征选取：

- 剪枝策略

    基于异常传播链路中两条连续的边对应的指标应该有相似的趋势，否则删掉后面的链接。
    
    在建立异常传播链路时，判断新加入 node 的相关系数，低于系数 x 时，node被剪掉。