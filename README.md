# 面试经验与考题整理

<p>2018/04/28 乐易网络</p>
<p>一面：使用Hadoop的MapReduce实现原理解题</p><br />
全国12亿人口年龄数据，数据格式为<城市，年龄>,求每个城市最大年龄，城市按首字母排序。
Input:12亿人口的数据分成12个map；Split:由于数据格式为<城市，年龄>,故不需拆分数据；Map(映射):同上；
Shuffle(派发)：将key值相同的分到一起去;[ 分到一起的key相同的由于不是在同一个DataNode里面，所以会被移动到同一个机器中去，最后形成一个list集合包含各种k-值，如{北京：Age1，Age2...}{City：Age1,Age2...}等等。] Reduce(缩减):把同一值的减少只剩一个，获得对应城市年龄集合，由此获得城市对应年龄的最大值。

本次面试看图写题，考察基本的逻辑处理和算法思想。
