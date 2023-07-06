# [MTAD-GAT: Multivariate Time-series Anomaly Detection via
Graph Attention Network](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=9338317)

## limitation
they do not capture the relationships between different time-series explicitly, resulting in inevitable false alarms.

## overview

时序预测和整个时间序列重构

The feature-oriented graph attention layer captures the causal relationships between multiple features, and the timeoriented graph attention layer underlines the dependencies along the temporal dimension.



### 1-D convolution
关注局部特征
使用Spectral Residual (SR)方法检测异常，并把异常值替换成正常值

### Graph Attention
#### Feature-oriented graph attention layer
全局的 metrics 特征 

#### Time-oriented graph attention layer:
全局的时序特征

### 特征融合


### Joint Optimization

### 
