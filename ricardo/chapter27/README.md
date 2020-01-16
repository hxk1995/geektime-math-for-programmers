# 决策树：信息增益、增益比率和基尼指数的运用
- 每道问题的区分能力不同，而我们对问题的选择会影响熵下降的幅度。这个幅度就是信息增益。如果问卷题的顺序选择得好，我们可以更快速地完成对用户性格的判定
##  如何才能进行高效的问卷调查。最核心的思想是，根据当前的概率分布，挑选在当前阶段区分能力更强的那些问题。
- 根据分组中的人物类型，为每个集合计算信息熵，并通过全部集合的熵值加权平均，获得整个数据集的熵。注意，一开始集合只有一个，并且包含了所有的样本
- 根据信息增益，计算每个问卷题的区分能力。挑选区分能力最强的题目，并对每个集合进行更细的划分。
- 有了新的划分之后，回到第一步，重复第一和第二步，直到没有更多的问卷题，或者所有的人物类型都已经被区分开来。这一步也体现了递归的思想。
- 决策树通常都只能把整体的熵降低到一个比较低的值，而无法完全降到 0。这也意味着，训练得到的决策树模型，常常无法完全准确地划分训练样本，只能求到一个近似的解。

##### 迭代二叉树 3 代（用信息增益来构建决策树的算法被）
- 它一般会优先考虑具有较多取值的特征，因为取值多的特征会有相对较大的信息增益
- 更多的取值会把数据样本划分为更多更小的分组，这样熵就会大幅降低，信息增益就会大幅上升。但是这样构建出来的树，很容易导致机器学习中的过拟合现象，不利于决策树对新数据的预测

### 基尼指数 （1 - p^2和）
- 基尼指数越高，分组越多，
### 总结
- 决策树算法的优势在于，容易理解和实现。此外，对于通过样本训练所得的树结构，其每个结点都是基于某个数据特征的判定，对于我们的阅读和解释来说都是很方便的。
- 决策树也有不足。之前我已经提到，这类算法受训练样本的影响很大，比较容易过拟合。在预测阶段，如果新的数据和原来的训练样本差异较大，那么分类效果就会比较差。

### 个人总结
- 信息增益、增益比率和基尼指数的运用，主要是用户解决信息的分类归纳整理的能力，分类越清晰当然越好，但也不是最好
- 主要理解 信息增益 熵 决策树 基尼指数 这几个概念