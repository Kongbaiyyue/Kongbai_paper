# Monte Carlo
[What is Mente Carlo Algorithm](https://www.zhihu.com/question/20254139)
## Monte Carlo Tree Search(MCTS)
[What is Mente Carlo Tree Search](https://www.jiqizhixin.com/articles/monte-carlo-tree-search-beginners-guide)
寻找最有潜力的下一步
放弃最优策略，最小化风险
围棋博弈其实是一个树搜索的过程，遍历的时候不需要将整棵树加载进来。
现在我们需要思考人类是如何考虑围棋或象棋等博弈的。给定一个根节点并加上博弈的规则，那么博弈树的其余部分就已经隐含表示出来了。我们可以遍历它而不需要将整棵树储存在内存中。在最初的根节点中，它是完全未展开的，我们处于博弈的初始状态，其余所有节点都没有被访问。一旦我们需要执行一个行动，我们就会思考采用该行动后会产生怎样的结果，因此访问一个节点后，需要分析该节点位置与带来的效用。