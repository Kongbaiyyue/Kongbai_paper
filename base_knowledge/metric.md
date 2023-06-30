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

# 