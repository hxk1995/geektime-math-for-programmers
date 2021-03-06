# 倒排索引/向量空间 =》 搜索引擎
### 搜索效率 
- 倒排索引，也是基于哈希表结构来设计的，属于一种布尔排序模型，它只考虑了单词是不是出现在文档之中，如果出现了就返回相应的文档，否则就不返回，对应于布尔模型中的真假值，相关性比较差
- 倒排索引就是把文档集转化为 关键词 ----》文档
### 检索出来的东西满足用户需求
- 利用向量空间模型，来衡量文档和用户查询之间的相似程度，确保两者是相关的。不过，向量空间模型需要涉及两两之间的比较，时间复杂度比较高。

#### 搜索引擎架构设计
##### 离线预处理
- 包括数据获取、文本预处理、词典和倒排索引的构建、相关性模型的数据统计等
- 倒排索引，设文章总数是 k，每篇文章的单词数量是 m，查询中平均的关键词数量是 l，但是除了原始数据，我们还需要额外的存储空间来放置倒排索引
##### 在线查询
- 不同的相关性模型，有不同的计算方式。最简单的布尔模型只需要计算若干匹配条件的交集，向量空间模型 VSM，则需要计算查询向量和待查文档向量的余弦夹角，而语言模型需要计算匹配条件的贝叶斯概率等等。
##### 倒排索引的设计
- 倒排索引里具体存储什么内容，
- 哈希表 key=>关键字   value => 链表（存储所有出现关键字的文章）  适用于布尔模型， 如果要实现空间向量就需要很多条件，概率计算/方差等等
- 如果要查询多个关键字存在于某一个文档中， 采用分治法对比每个关键词存在的文档列表集合
- 多个关键词的查询结果如何取交集
##### 倒排索引和向量空间的结合
- 不怎么懂，具体要设计两种算法可以互相依赖的部分，从而提高效率，哎 需要具体的设计