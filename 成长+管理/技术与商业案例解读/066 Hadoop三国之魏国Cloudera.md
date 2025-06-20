# 066 Hadoop三国之魏国Cloudera

今天开始，我打算介绍一下Hadoop领域里面的三家发行商，它们之间的关系正好和三国时候的魏蜀吴很类似，所以不妨就排演一出Hadoop的三国版，带你一起感受和思考下大数据领域的发展和乱相。

首先出场的是魏国Cloudera。我们知道三国时的魏国，曹操以"挟天子以令诸侯"而知名。这句话用在Cloudera身上不是太合适，不如说"天子"，也即Hadoop的第一个作者，和Cloudera联合在一起，来试图"令诸侯"更为贴切。我们姑且将就一下吧，历史总是惊人得相似，但也只能到相似的程度了。

Cloudera成立于2008年，由克里斯托夫 · 比塞格利亚（Christophe
Bisciglia）、埃姆 · 阿瓦达拉（Amr Awadallah）以及杰夫 · 哈默巴赫（Jeff
Hammerbacher）创建。如今阿瓦达拉还是CTO，哈默巴赫虽然挂着首席科学家的头衔，但很少参与公司管理了，而比塞格利亚则混迹于硅谷IT圈。

2012年大数据的概念才开始红火起来，2008年他们几位就能够看到这个市场并创立公司，实在是值得敬佩。

2009年3月发生了Cloudera创立以来第一件比较大的事件：第一笔融资到账。这笔500万美元的融资，是由全球知名的五大风险投资机构之一的Accel
Partners提供的。Accel
Partners这个投资者，在后面的几轮投资里面都扮演了重要角色。我想它最后一定是赚了不知道多少倍的钱。

**伴随融资的到来，Cloudera发行了它的第一个Hadoop集成版。涉及Cloudera的盈利方式，我们需要展开讲一讲它的Hadoop集成版。**

现在业界通常也把Cloudera发行的Hadoop版本叫作CDH，CDH里面的东西本身都开源，也可以从Cloudera官网获得。但是除了CDH发行版以外，Cloudera还有一些私货，这些就是Cloudera独有的了。

Cloudera的创始人在一次访谈中提到，2008年他们创建公司的时候，打算做的服务类似于现在AWS的Elastic
MapReduce，通过在云上给大家提供服务来赚钱。然而他们很快就发现这个模式太超前，在2008年的时候不切实际，而且投入也很大，所以就转向了做Hadoop发行商的角色。

**所谓的Hadoop发行商，有点类似于Linux世界里的RedHat。公司通过开源软件的包装，整合稳定的版本形成一个套餐，通过让企业用户购买套餐来实现盈利。**

企业用户愿意购买套餐无非是两个原因：一是为了对方提供的技术支持，二是对方的套餐里面有一些开源版本没有的东西，可以方便企业使用和部署这个开源的版本。

Cloudera的盈利模式就来自于这两方面。Cloudera给企业提供技术支持，而这些技术支持是要通过购买收费套餐获得的。

Cloudera的价格不便宜，最新的价格差不多是1万美元一个节点一年。这个价格是相当高了，所以Cloudera在我国卖的时候，常常是用户只愿意买10个节点，回头自己就跑上几百个节点。盗版软件曾经一度横行，免费多用节点也就不是什么难事了。国内大致就是这个情况了。

Cloudera在盈利模式上还依赖于套餐里面拥有的非开源的东西。Cloudera的CDH是100%开源软件整合，在网站上可以免费下载使用。但是Cloudera同时又提供了一个叫作Cloudera
Manager的企业管理组件，这个东西是不开放源代码的，在三个月试用期过后就要收费了。它提供了企业比较在乎的对计算机集群的管理、部署、升级、监控等各方面的功能。

这些功能对于普通用户，尤其是喜欢折腾的用户来说可能无所谓，但是Cloudera相信这些功能对于真正有钱的企业来说必不可少，而开源的Hadoop版本里面最差的就是这部分。

Cloudera相信，他们自己做的这个Manager，能够比其他Hadoop发行版更有价值，更加适合企业级用户使用。

**等到2009年9月，Cloudera又一次的大手笔震惊了IT界。他们请到了一尊"大神"------道格
· 卡丁（Doug Cutting）。**

这位大神是"Hadoop之父"，第一位作者。开始他是自己自娱自乐写Hadoop，后来被雅虎这个"活雷锋"招安，带领一队人马做Hadoop。有关大神的故事长篇累牍，讲也讲不完，因此这里就不展开了。

据说，因为在此之前卡丁和他的顶头上司，雅虎里面管Hadoop的那个副总裁之间互相看不顺眼，经常被对方鄙视或者穿小鞋，大神心里早就不爽了。于是Cloudera手一招，大神就毫不犹豫地跳过来，成了首席架构师。当然还有一个说法，那就是Cloudera给了很多钱很多股票。

至于哪个版本为真，其实不重要了。不管怎么样，大神现在肯定是发财，发大财了。至少如果大神一直继续在雅虎，肯定赚的比现在少很多。大神做了Cloudera的首席架构师以后，日子是过得顺风顺水，后来还荣升了著名的Apache基金会的主席。

自从有了卡丁以后，Cloudera腰杆也直了，底气也足了，从此以后就以"Hadoop正宗"自称了。

这个故事有点类似于曹操拿着天子做文章，但不同的是天子算是被曹操胁迫的，而"大神"和Cloudera这几个与Hadoop最初版本没太多关系的创始人之间，多少应该算是互相捧场，皆大欢喜。

**好日子开始了，Cloudera不断烧钱壮大，到了2011年又开始了新一轮融资，这次的融资引入了一个特别值得注意的角色：In-Q-Tel。**

国内的朋友对In-Q-Tel可能不太熟悉，这个金主是CIA下面的投资公司，专门投资对美国国家安全有重大意义的项目。其中著名而神秘的大数据分析公司Palantir，美国棱镜项目技术提供者的启动资金就是这家基金给的。另外，MongoDB也接受过他们的钱，所以印度觉得MongoDB不安全。而有了这个机构的投资，到底是不是还安全，这只能是"公说公有理婆说婆有理"了。

**这次Cloudera拿到了4000万美金。有了这么大一笔钱，Cloudera迎来了一次大发展。这次Cloudera意识到Hadoop需要一个更快的查询引擎，并高调宣布要做一个MPP的产品，也就是Impala。**

这也是Cloudera在宣传口号上的一次调整。以前Cloudera总是称自己为Hadoop发行商，这次它华丽丽地改名了，从此以后表示自己是个数据仓库公司，而Impala则是他们大力推进的查询系统。

Imapla可算是命不太好。最开始，Cloudera试图让Impala成为自己控制的项目，所以并没有将其交给Apache，于是Impala也就没有得到Cloudera以外人士的重视。结果，其他很多的竞争对手就这样起来了，尤其Spark更是攻城略地。等到后来Impala被贡献给Apache时，已经是为时太晚。

**2014年是Cloudera的丰收年。这一年里，英特尔以7.5亿美元的价格拿走了它18%的股权。跟随英特尔的还有谷歌、戴尔公司老总迈克尔
· 戴尔（Michael
Dell）的私人投资基金，以及其他各路人马。这次投资也把Cloudera的总估值送上了41亿的巅峰，让Cloudera当之无愧地坐上了Hadoop发行商里的第一把交椅。**

**为了坐实数据仓库公司的梦想，Cloudera又开始了另外一个项目Kudu，即2015年开始主推的新一代存储系统**。Kudu的想法是让Cloudera有一个可以同时支持OLAP和OLTP查询，两者性能又都不会太差的存储引擎。这个项目引起了广泛关注，并让Cloudera再次吸引了大量的注意力。

然而俗话说得好，盛极必衰。此后的三年里，Cloudera的业务并没有随着"大数据"这个概念进一步膨胀，相反的，它的估值到底值不值41亿美元，一直让人有些揪心。

Cloudera终于走向了上市之路，而这个过程可谓非常曲折，因为上市消息宣布以后，大家首先注意的是上市材料里面的估值并没增加。**2017年，Cloudera自砍估值一半，上市以后的估值只有20多亿**。别人不知道，起码英特尔的投资是彻底亏了。

这种拼命也要上市的做法，充分反映了Cloudera可能遇到了什么问题。从各方面来看，这可能主要还是现金流的问题，缺钱却没有投资人愿意继续投入了，只能血淋淋地上市了。上市后的Cloudera并没有飞起来，可能大家都还希望给它一点时间，看看它到底能做多好吧。
