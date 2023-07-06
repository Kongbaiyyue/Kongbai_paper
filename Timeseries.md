### 时序预测需要什么样子的模型

到底哪个模型更加适合时序预测呢？我们会依次分析RNN、Transformer、Linear三类模型。

- 关于RNN
大家可以首先回忆一下RNN模型有什么好处。我第一次接触RNN的时候，很不喜欢它，因为它对序列依赖设定了马尔可夫假设，感觉这样的设计丢失太多信息了，但是又不得不使用它，因为它在序列维度上参数共享，因此天然可以处理变长数据（Varied-Length sequence），这对序列建模非常重要。甚至直到现在，RNN依然被广泛使用在视频预测问题上。

- 关于Transformer
当Transformer模型出现之后，它完美兼顾了“处理变长数据”（注意力机制自身的可扩展性）以及“建模长期依赖”（点点时序连接），所以它很适合做序列建模，这也是为何近几年的NLP领域，Transformer呈现主导地位。但是在时序预测领域，像我几个月前首答时提到的，这种点点连接的零散建模打破了时间序列本身的连续性，所以我们做了Autoformer来建模序列级别的时序关联。

- 这个大家应该相当熟悉了，我们的深度学习都是从MLP学起的。它最开始提出是用于特征映射，也就是将数据映射到高维空间。使用MLP去做序列建模可以吗？当然可以，一些工作已经证明了其有效性，比如N-BEATS等。但是我个人认为不优雅（仅仅为个人喜好），因为它不具有处理变长数据的能力，MLP的模型参数和所建模的序列关联是绑定的，这样的模型我觉得是不够灵活的。同时，如果序列变长的话，模型参数量随序列长度的增加也是二次的，大家可以估计一下长序列情况下带来的参数量代价（注意RNN和Transformer的参数量都是和序列长度无关的）。

### 时序预测模型选择

综上，我觉得模型本身是各有所长的，如果现在给我一个实际问题，根据我的经验我会做出以下选择：

- 如果是视频预测，我肯定直接选择RNN+CNN，比如ConvLSTM、PredRNN、MotionRNN等；
- 如果是时序预测，短时的话（需要预测未来10个时刻之内），我可能会尝试一下RNN，但是如果是长时，我会选择Autoformer；
- 如果是特征分类，我毫不犹豫选择MLP。

所以，我认为深度模型是否适配于某类任务，应该从架构本身的归纳偏好出发去分析。如果仅仅看几个标准数据集上的实验结果的话：

- 小规模试验有太多Tricky和Unconsistency的成分在；
- 当前的一些设计可能无法充分发挥某类深度模型的能力；
- 检验模型优劣的唯一方法是用于实际业务。

### IMS和DMS的比较
与DMS预测结果相比，由于采用了自回归模式，IMS预测的方差较小，但不可避免地会受到误差累积效应的影响。因此，当有一个高度准确的单步的predictor，且T相对较小时，IMS更可取。相比之下，当难以获得无偏的单步预测模型或T较大时，DMS预测会生成更准确的预测（make sense）。

## paper
### 时序异常检测
[Multivariate Time-series Anomaly Detection via Graph Attention Network](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=9338317) ICDM2020

[Log-based Anomaly Detection with Deep Learning: How Far Are We?](https://arxiv.org/pdf/2202.04301.pdf) ICSE2022

[DeepSyslog: Deep Anomaly Detection on Syslog Using Sentence Embedding and Metadata](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=9865986) TIFS2022 网络与信息安全

#### 多模态时序异常检测
[Identifying Bad Software Changes via Multimodal Anomaly
Detection for Online Service Systems
](https://netman.aiops.org/wp-content/uploads/2021/09/SCWarn.pdf) FSE/ESEC2021


