# 079 微软的大数据发展史：Azure的大数据发展

## 一、HDInsight：一个云端Hadoop版本

Azure是微软云计算的品牌，而云计算是给客户提供服务的。所以，微软云计算平台的大数据发展方式，与其他解决内部需求的项目不同，最初主要围绕Hadoop生态圈展开。

Hadoop诞生时，没有考虑过Windows上稳定运行的问题，因为做Hadoop的企业是雅虎、Facebook、LinkedIn等湾区互联网企业，这些企业都用免费的Linux，不用昂贵的Windows，它们没必要考虑Hadoop在Windows下运行的问题。

但是，Hadoop的壮大让微软感受到了危机。如果每个使用Hadoop的企业都用Linux了，数据就会被存到Linux里，各种应用服务也有可能就渐渐转向Linux。

微软担心大数据系统的出现和普及，尤其是Hadoop生态圈的壮大，会威胁到Windows的销售，导致Windows服务器的业务下降。因此微软云计算部门选择了和Hortonworks合作，把Hadoop在Windows上的稳定运行当作头等大事对待。

微软云计算部门和Hortonworks对接的，是微软内部负责研发一个叫作HDInsight的云端Hadoop版本的团队。这个团队有两大任务：其一是和Hortonworks一起，实现Hadoop在Windows上的稳定运行；其二是为微软提供云端的Hadoop版本，也就是HDInsight。

从微软给这个团队定义的任务出发，HDInsight团队很好地完成了这两个任务。但是HDInsight有一个比较大的问题：性能差。简单来说就是，**HDInsight在对接Hadoop文件系统和微软的云存储Azure
Blob Store时，对接得不是很高效，因此HDInsight的运行效率很低。**

HDInsight作为云端的产品，不但对外推广，也在内部大量寻找用户，但是因为性能问题内部用户寥寥无几，没有部门愿意买单。

我在上一篇文章中提到过，必应部门做了一个数据分析平台Cosmos。这个平台和HDInsight比起来，优势主要就体现在性能上。而且，Cosmos作为数据分析工具，只要能分析数据就好，不需要考虑是不是兼容Hadoop。因此，Cosmos在和HDInsight的对标中，除了一些政治因素外，其他方面鲜有败绩。

## 二、 Azure Data Lake的诞生

很长一段时间里，HDInsight和Cosmos在微软内部都是竞争对手，双方都希望微软的各大部门采用自己的平台，然而HDInsight因为性能问题每战必输。

而在Cosmos被合并到云计算部门后，这两个产品同处在了一个组织下面，输赢不再重要，竞争关系也不复存在了。但是因为长期竞争的关系，两个团队私下并不和谐。

Cosmos被重组到云计算部门后，微软聘请了著名的数据库领域的专家，前威斯康辛大学教授、前雅虎副总裁拉
· 罗摩克里希纳恩（Raghu
Ramakrishnan）领导这个团队。为什么聘请这个人，因为云计算部门想做一款新产品，我们姑且简单地理解为是做一款面向外部客户的Cosmos吧。

这个新的团队领导认为，对外服务的Cosmos是一款可以连接和处理Azure上所有数据源的数据查询引擎。因为他的这个想法，就需要对Cosmos做伤筋动骨的改动。

这样大的改动只获得了一部分人的支持，这些人得到了升迁和资源。而持反对意见的人，慢慢淡出了权力中心，陆续离开微软，我也正是在那个时候去了Tableau。

然而，这个Cosmos新版本的开发难度远远超出了他的心理预期，交付日期一拖再拖。2016年，这个产品在延期两年后终于以Azure
Data Lake这个名字发布了。

无论微软内部和外部，这个团队都极力推动这款产品，但买账的人并不多。微软内部大部分选择了老版本的Cosmos不肯搬迁，在外部也只有沃尔玛买单。为什么会是这样一个结果呢？

这个系统失败的原因有很多，在我看来主要有以下两点。

1.  用户需要重新学习一种叫作U-SQL的语言，才能充分发挥这个系统的性能。U-SQL其实是SCOPE的改造版，但改造得不伦不类。为什么这么说？首先是SCOPE语言很灵活，但U-SQL却很死板。其次是SCOPE在数据类型上向C#兼容，而U-SQL却决定一半的地方兼容SQL，另外一些场景兼容C#，兼容规则因此搞得非常复杂。
2.  这个系统和C#紧紧地绑定在一起，而Hadoop生态圈完全基于Java，于是鲜有用户愿意尝试这个系统。

## 三、大数据平台CosmosDB

云计算部门的另外一个大数据平台是DocumentDB，它是市面上很少见的可以和MongoDB竞争的产品。有关DocumenDB的功能分析，我在之前的文章里已经讲过。

DocumentDB在后来的一次升级中被改名为CosmosDB。这次升级的主要目的是把数据模型从MongoDB一种提升到了若干种，包括MongoDB的半结构化数据、图数据库等，从而使CosmosDB能够更灵活地支持不同的应用。

CosmosDB推出时，市面上还找不到同类竞品。当然，这个说法其实不完全准确，因为开源社区在2012年曾经有一个叫作FoundationDB的项目，和CosmosDB的做法很像，底层是统一的存储方式，上面支持不同的数据模型。但是FoundationDB被苹果收购之后就不再开源，一直到2018年5月这才重新开源出来。这种产品的独特性给了微软一个很好的市场切入点。

微软的云计算部门在CosmosDB上投入相当大。作为MongoDB的竞品，CosmosDB也表现出了良好的性能和扩展性，并解决了MongoDB长期以来为人诟病的安全问题。因此，CosmosDB发布之后业务量一直迅猛增长，最终成了微软大数据服务里面唯一的亮点。又因为这是一个只在Azure上发售的服务，一定程度上也给Azure带来了不少的流量。

在2018年5月刚结束的年度微软开发者大会（Microsoft
Build）上，CosmosDB作为大数据领域唯一被大会主题报告提及的业务，展示了非常靓丽的业绩。而且，微软今年又为CosmosDB增加了全球多节点同时写入的功能。这一切都说明，CosmosDB业已成为微软云端大数据产品线上最为耀眼的一款产品。

总体上来说，微软云计算部门的大数据之路：无论是拥抱开源的HDInsight，还是自己努力研发的Azure
Data Lake，又或者是具备独特地位的CosmosDB，投入都是巨大的。

但目前来看，只有CosmosDB既具有特色又很成功，其他产品就不过尔尔了。HDInsight的性能问题，Azure
Data Lake的定位问题，都是微软云计算部门大数据上表现欠佳的地方。

在大数据时代，微软不可谓不努力，但是产品的表现参差不齐，没有表现出一个曾经的软件帝国的创造力和统治力。所以，一个公司如果成为时代的追随者，是很难在产业中有统治地位的。CosmosDB是这些产品里少有的亮点，一方面是因为解决了客户的实际需求，一方面是产品有独特的竞争优势。

因此，我们可以看到，在大数据时代，创新，尤其是解决实际需求的创新，依然是一个公司确立行业优势最重要的因素。
