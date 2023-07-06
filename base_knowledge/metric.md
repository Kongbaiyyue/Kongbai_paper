# nlp

## tf-idf
[wikipedia](https://en.wikipedia.org/wiki/Tf%E2%80%93idf)

tf-idf是一种信息检索与文本挖掘技术

$ tf-idf_{i,j} = tf_{i,j} \times idf_i $

词频 $ tf_{i,j} $ 表示单词 $i$ 在文本 $j$ 中出现的频率

计算公式：$ tf_{ij} = \frac {n_{ij}} {\sum_k n_{k,j}} $

$ n_{ij} $ 是词 $ t_k $ 在文件 $ d_j $中出现的次数，分子 $ n_{i,j} $是该词在文件 $ d_j $ 中出现的次数，分母是文件 $ d_j $ 中所有词出现的次数之和。

逆向文件频率用来衡量一个词普遍重要性，出现在其他文件中越少，在该文件的重要性越高。
计算公式：$ idf_i = \lg \frac {|D|} { | \{ j : t_i \in d_j  \} | } + 1 $

$ | \{ j : t_i \in d_j  \} | + 1 $ 防止词不在语料库中，分母为 0 

# binary classification
## Accuracy、Precision、Recall、F1
| |   Truth Positive  |  Truth Negtive |
|  ----  | ----  | ---- |
| Predict Positive | TP  | FP |
| Predict Negtive  | FN  | TF |

$ Precision = \frac {TP} {TP + FP} $
精确率 (Precision)：你认为的该类样本，有多少猜对了（猜的精确性如何）。

$ Recall = \frac {TP} {TP + FN} $
召回率 (Recall)：该类样本有多少被找出来了（召回了多少）。

$ Accuracy = \frac {TP + TF} {TP + FP + FN + TF}$
准确率（Accuracy）：有多少预测正确了

## Precision-Recall（P-R）曲线
[P-R、ROC、DET 曲线及 AP、AUC 指标全解析](https://zhuanlan.zhihu.com/p/99085220)

正例数记作$ n_+ = TP + FN $

负例数记作$ n_- = FP + TF $

纵轴为Precision、横轴为Recall

$ P_+ = \frac {TP} {TP + FP} $
$ R_+ = \frac {TP} {TP + FN} = \frac {TP} {n_+} $

如下例：
![阈值设在各个位置时，正类查准率 P+ 与查全率 R+ 的数值](https://pic2.zhimg.com/80/v2-7e940687b38767d5301d47053f7c780d_720w.webp)

其对应的 P-R 曲线
![P-R 曲线](https://pic1.zhimg.com/80/v2-0c25879747be217c63bc104dced0a1b8_720w.webp)

从宏观上看，$ P_+ $ 、$ R_+ $ 是鱼与熊掌不可兼得的关系，所以 P-R 曲线呈现单调下降的趋势；但越好的二分类器，其 P-R 曲线会越接近图像的右上角。

##  Receiver Operating characteristic Curve（ROC） 曲线
ROC 的纵轴叫作 true positive rate（$ TP\% $）即在所有的正例中，有多大的比例被正确地分类为正例，横轴叫 false positive rate（$ FP\% $）即在所有的负例中，有多大的比例被错误地分类为正例。

$ TP\% = \frac {TP} {TP + FN} = \frac {TP} {n_+} $

$ FP\% = \frac {FP} {FP + TN} = \frac {FP} {n_-} = 1-R_- $

