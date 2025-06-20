# 145 SAP的HANA战略（上）

SAP是总部位于德国的全球最大的ERP公司。作为一家重量级的企业应用软件公司，SAP曾经有过一段风光的日子。

但是而后的日子也开始不好过起来。

日子不好过的主要原因是SAP的软件需要跑在数据库上，而备选的数据库一般来说不是IBM的DB2，就是Oracle。本来两者和SAP的软件配合，相得益彰，曾经一度合作得很愉快。但随着Oracle开始进军企业级软件市场，把手伸到SAP的地盘来，SAP的日子就开始不好过起来。

Oracle在21世纪初进行了一系列的并购，包括收购了Siebel和仁科等重要的企业级软件企业，把自己从底层数据库到企业级软件的体系补全了。这样一来，SAP就麻烦了，因为自己的软件依赖于对方的数据库，而对方却还能够提供类似的企业级软件。

好在还有一个IBM的DB2可以用。SAP一度和IBM合作，希望两者的结合可以给自己带来所谓的强强联合。但是IBM的DB2却一直面临着诸多问题，比如本身就不是市场上最好的数据库，人才流失又很严重。所谓的合作开展起来，效果却非常有限。

在这个背景下，SAP开展了一场技术与忽悠并存的战略大跃进，也就是SAP著名的HANA战略。HANA的出现对SAP和业界都产生了巨大的影响。其实施的过程可谓精彩绝伦，堪称一部大制作的"影片"。

今天我就来讲一讲这个SAP的HANA战略。

让我们先把时间倒回到2009年。这一年，数据库的两大顶级会议之一的SIGMOD在罗德岛召开。我最后一次以PhD的身份参加SIGMOD，所以对这个会议印象深刻。这种会议一般都会有赞助商。出钱多的金主很多时候会给一个Keynote的讲座。

2009年的金主是SAP。这多少有点让人大跌眼镜。一个做企业级软件的公司，来一个数据库顶级会议上大把撒钱，怎么看怎么怪。

在这次大会上，SAP董事会主席兼创始人之一的哈索·普拉特纳（Hasso
Plattner）给了这样一个Keynote：A Common Database Approach for OLTP and
OLAP Using an In-memory Column
Database。这个Keynote宣告了SAP要搞一个内存数据库，它的名字叫HANA。

SAP要搞数据库，这可是一件大事情。一个做应用软件的要进军数据库市场，说明"兔子急了要咬人"了。但是企业级软件毕竟是应用软件，而数据库是基础架构软件。就像一个"做菜高手"突然说要开始"杀鸡"，先不说对方哪里来的底气，最起码外界对这个"做菜高手"的看法，肯定是见仁见智的。

HANA是High-Performance Analytic
Appliance的简称。SAP要做的这个数据库，作为一个"做菜高手"进军"杀鸡市场"的第一炮，打得很响亮。按照SAP的宣传，它有着市面上传统的数据库很多不具备的特性。

下面我们可以一起了解一下这些特性，这很有必要。

**第一，HANA选择了按列存储的同时支持事务处理**。传统数据库是按行存储的，数据仓库近些年来才开始按照列式存储。按行存储对事务处理方便，但是不利于分析处理；按列存储则相反。但是这两者的不利于程度是有所不同的。

通常来说，一个数据库如果同时支持事务处理和分析处理，那么数据库厂商会选择按行存储，因为按列存储的同时支持高效率的事务处理是非常难的。但是HANA却选择了按列存储的同时还支持事务处理，这个用数据库界"老司机"的话来说就是，要么是艺高人胆大，要么是无知者无畏。

**第二，做出把所有的数据都放在内存里这个假设**。今天来看，内存不是很贵了，但是在2009年敢做出那样的假设胆子就不是一般的大了。一个数据库一旦数据都在内存里，很多传统数据库的基本假设就都不一样了，做法当然也就很不一样。

所以HANA在很多演示的时候，查询极快。一个在Oracle或者DB2上需要跑一天才能做出来的报表查询，在HANA那儿3秒钟搞定。对，就是这么快。当然，其实查询是精心挑选的，能够存储这么多数据的机器的配置是非常高的。

**第三，因为HANA选择了在一个系统同时支持事务处理和分析查询，这就让HANA的数据不需要额外ETL，企业也不需要为分析查询专门配备另外一份列存的数据**。某种程度上，HANA宣称自己节省了企业的消耗，也是对的。而且因为两者共享数据，分析查询的时候能够查询的数据就非常新了。这对企业来说也是非常有必要的。

**第四，HANA几乎完整地整合了R的功能，并且把SAP业务相关的很多功能直接在HANA内部实现了**。这有点反计算机软件构架里面的封装。然而在内存数据库的环境下让数据离业务相关计算更近，无疑是一种效率上极其有效的策略。

**第五，HANA采用了现代数据库里常用的Shared-nothing的体系架构**。这种体系架构数据被纵向按照某个主键切分，每台机器只需要负责自己的部分。这让HANA具备了非常灵活的资源配置，而且加了机器查询也就会变得更快，立竿见影。简而言之，HANA的体系架构很新。

综上所述，HANA在技术上是很有创新的，而且单纯从SAP公布出来的这些技术细节来看，HANA的确是具备了在很多方面对传统数据库发起挑战的能力。所以，一个"做菜"的，看起来"杀鸡"也杀得很漂亮。很多人不得不为SAP精彩的HANA数据库疯狂打Call了。

由于SAP的这个举措，首先受到伤害的是和SAP合作的IBM的DB2组了。毕竟，本来是难兄难弟抱团取暖，现在变成了一个人冲锋陷阵，抛弃了老伙伴。

其次受到威胁的当然是那个坐在数据库领域第一把交椅上的Oracle。试想一下，原来用SAP的必须上Oracle，而用Oracle的还可以搭自己家里的企业级软件。这让Oracle处于多有利的地位呀！但突然之间局势就变了，SAP有自己的数据库了，而且还很快、很厉害、很先进。接下来Oracle的这个生意就不好做了。

但是对2009年的SAP来说，HANA这个吸引眼球的宣传，一下子让原本已经成为或者即将成为二流公司的SAP回到了聚光灯前，不管产品有没有做出来，最起码先把风头抢占了。接下来，大家关注的就是SAP会做出一个什么样的产品来，是让大家刮目相看，还是烂泥扶不上墙呢？
