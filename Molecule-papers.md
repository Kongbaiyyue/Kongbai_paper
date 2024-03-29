# Retrosynthesis

## 断键补全

### 断键

### 补全

## 直接端到端的训练

# 特征 [Chemistry-informed molecular graph](https://www.pnas.org/doi/epdf/10.1073/pnas.2212711119)
## 经验知识
溶剂和催化剂 (决定了反应类别 reaction type)

## 内在特征
- NMR chemical shift
- bond dissociation energies
- one or a few atom to reaction
- 


## Input2Output
### Graph2Graph
- [MEGAN: Molecule edit graph attention network: modeling chemical reactions as sequences of graph edits. Mikołaj Sacha;Mikołaj Błaż;Piotr Byrski;Paweł Dąbrowski-Tumański;Mikołaj Chromiński;Rafał Loska](https://pubs.acs.org/doi/pdf/10.1021/acs.jcim.1c00537) JCIM2021 sci-2
- [GraphRetro: Learning Graph Models for Template-Free Retrosynthesis. Vignesh Ram Somnath;Charlotte Bunne;Connor W. Coley;Andreas Krause;Regina Barzilay](https://grlplus.github.io/papers/61.pdf) ICML2020 ccf-A
- [G2G: A Graph to Graphs Framework for Retrosynthesis Prediction. Chence Shi;Chence Shi;Hongyu Guo;Ming Zhang;Jian Tang](http://proceedings.mlr.press/v119/shi20d/shi20d.pdf) ICML2020 ccf-A
- [GLN: Retrosynthesis Prediction with Conditional Graph Logic Network. Hanjun Dai;Chengtao Li;Connor W. Coley;Bo Dai;Le Song](https://proceedings.neurips.cc/paper/2019/file/0d2b2061826a5df3221116a5085a6052-Paper.pdf) NeurIPS2019 ccf-A

### Graph2SMIILES

### SMILES2SMILES
- [RETROFORMER: pushing the limits of end-to-end retrosynthesis transformer. Yue Wan; Benben Liao; Chang-Yu Hsieh1;  Shengyu Zhang2](https://arxiv.org/pdf/2201.12475.pdf) ICML2022 ccf-A
- [RetroDCVAE:Modeling Diverse Chemical Reactions for Single-step Retrosynthesis via Discrete Latent Variables](https://dl.acm.org/doi/pdf/10.1145/3511808.3557397) CIKM2022 ccf-B

### chanllenge
- many previous papers have pointed out the limited diversity of sequence to sequence models in other domains.

## template
- [Improving Few- and Zero-Shot Reaction Template Prediction Using Modern Hopfield Networks.Philipp Seidl; Philipp Renz; Natalia Dyubankova; Paulo Neves; Jonas Verhoeven; Jörg K. Wegner;
Marwin Segler; Sepp Hochreiter; and Günter Klambauer](https://pubs.acs.org/doi/pdf/10.1021/acs.jcim.1c01065) JCIM2021 sci-2 [blog](/Molecule/Retrosynthesis/Improving%20Few-%20and%20Zero-Shot%20Reaction%20Template%20Prediction%20Using%20Modern%20Hopfield%20Networks.md)

### template-based

### template-free

### semi-template-based

## prepare read
- [MIND THE RETROSYNTHESIS GAP: BRIDGING THE DIVIDE BETWEEN SINGLE-STEP AND MULTI-STEP RETROSYNTHESIS PREDICTION](https://arxiv.org/pdf/2212.11809.pdf)
- [Artificial Intelligence for Retrosynthesis Prediction](https://reader.elsevier.com/reader/sd/pii/S2095809922005665?token=13DEE7726C507F6FA06C2C6B0A941476D5D09D9174F0F0A44B76C6AA7A2FF1E5C5BD44EEF941BA248CC8E581AF52D639&originRegion=us-east-1&originCreation=20230331030330)

## molecule grammar
- [G-MATT: Single-step Retrosynthesis Prediction using Molecular Grammar Tree Transformer](https://arxiv.org/pdf/2305.03153.pdf) 2023arxiv


# Molecule Pretrain
- [Chemformer: a pre-trained transformer for computational chemistry. Ross Irwin;Spyridon Dimitriadis;Jiazhen He;Esben Jannik Bjerrum](https://iopscience.iop.org/article/10.1088/2632-2153/ac3ffb/pdf) Machine Learning: Science and Technology2022
- [PanGu Drug Model: Learn a Molecule Like a Human. Xinyuan Lin;Chi Xu;Zhaoping Xiong;Xinfeng Zhang;Ningxi Ni;Bolin Ni;Jianlong Chang;Ruiqing Pan;Zidong Wang;Fan Yu;Qi Tian;Hualiang Jiang;Mingyue Zheng;Nan Qiao](https://www.biorxiv.org/content/10.1101/2022.03.31.485886v1.full.pdf) 2022


# Molecule Generation
- [Data-efficient Graph Grammar Learning For Molecular Generation. Minghao Guo; V eronika Thost;Beichen Li;Payel Das;Jie Chen;Wojciech Matusik](https://arxiv.org/pdf/2203.08031.pdf) ICLR2022 ccf-A

