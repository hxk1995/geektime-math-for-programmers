# 30 | 统计意义（上）：如何通过显著性检验，判断你的 A/B 测试结果是不是巧合？

现在互联网公司往往会根据用户的在线行为来评估算法的表现，但是在线测试有个很大的挑战就是如何排除非测试因素的干扰。

比如一个新 feature 上线之后数据带来了增长，你并不确定是否是因为这个 feature 或者是因为某些网络事件导致的。

通过 AB test 可以得到更具备说服力的数据，但仍然可能存在问题。因为本身 AB 两组仍然是抽样数据，如果在 A 组都抽到了正态分布偏右的值，而 B 组都是偏左的值可能得出完全相反的结论。

如何利用统计学更好的更科学的判断这个结果的有效性呢？需要先理解下面概念。

## 显著性差异

显著性差异（Significant Difference），其实就是研究多组数据之间的差异，是由于不同的数据分布导致的，还是由于采样的误差导致的。

假如我们已知 A、B 两个数据的分布，假设 A 分布的均值小于 B 的分布，但是两者的方差一致，那么 A 分布随机产生的数据有更高的概率小于 B 分布随机产生的数据。

- 差异具有显著性：表示不同的组很可能来自不同的数据分布
- 具有显著差异：指差异的幅度很大

## 统计假设检验和显著性检验

统计假设检验是指事先对随机变量的参数或总体分布做出一个假设，然后利用样本信息来判断这个假设是否合理。在统计学上，我们称这种假设为虚无假设（Null Hypothesis），也叫原假设或零假设，通常记作 H0。而和虚无假设对立的假设，我们称为对立假设（Alternative Hypothesis），通常记作 H1。也就是说，如果证明虚无假设不成立，那么就可以推出对立假设成立。

统计假设检验会先认为原假设成立，然后计算结果。若在单次实验中产生了小概率事件，则拒绝原假设而接收对立假设。一般小概率是 < 0.05 的事件，有时候也会取 0.1 或者 0.01。

## P 值

P 值中的 P 代表 Probability，就是当 H0 假设为真时，样本出现的概率，或者换句话说，其实就是我们所观测到的样本数据符合原假设 H0 的可能性有多大。

P 值很小说明观测值与假设的期望值有很大的偏离，所以原假设发生的概率很小，我们就倾向于拒绝原假设，接收对立假设。反之亦然。

其实显著性检验的具体方法有很多，例如方差分析（F 检验）、t 检验、卡方检验等等。不同的方法计算 P 值的方法也不同，在下一节，我会用 A/B 测试的案例来详细解释。

## 思考题

会趋向于一致。