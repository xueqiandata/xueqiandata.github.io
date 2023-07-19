不知从何时起，它已经在这里很长时间了。

![image-20220718141608296](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/image-20220718141608296.png)



这么重要的位置，其重要性可见一斑。

或者说，至少微软想让其变得重要。

![包含 Microsoft Power Platform 概述的图表。](https://docs.microsoft.com/zh-cn/power-apps/maker/data-platform/media/data-platform-cds-intro/platform.png)

Power Platform包含的5大组件，全都需要数据作为粮食投喂。

而数据来源，上图提供了3个。

数据连接器：通过各式各样的链接器，链接来自不同数据源的各式数据。这是打通与第三方世界数据的壁垒。

AI：这是未来发展趋势，AI人工智能获取那些非结构化的模型以得到数据。

Dataverse：数据存储的元宇宙。不仅仅是个数据库。



熟悉SharePoint的，几乎都会用过list，这是管理文档和一些简单数据列表比较好的系统。然而创建一些表之间关系或者一些基于对象的数据时就无能为力了。Access目前已经很少有人在用。SQL server虽然安全性和处理关系型数据的能力强大，但是毕竟想要驾驭SQL需要深厚的技术能力。

于是Dataverse出现了。

关于Dataverse的具体来历、功能如何强大、如何建立表和表之间的关系，我们暂且按下不表。

今天只来说一说从Power BI中如何获取Dataverse里的数据，以及想要使用Dataverse需要的条件。

1、点击Power BI主页上的“数据”工作区的Dataverse：

![image-20220718141608296](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/image-20220718141608296.png)

当然，前提是你已经有了Power BI账号，并且已经有了Dataverse数据表。（别急，后面会说）

2、选择想要导入的表格，勾选并加载

![image-20220718155716774](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/image-20220718155716774.png)

3、选择数据连接模式

建议直接选择DirectQuery直连模式，为方便以后我们的数据修改与获取操作。

![image-20220718155817535](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/image-20220718155817535.png)

4、选择合适的列进行可视化呈图

![image-20220718160633428](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/image-20220718160633428.png)

整个过程其实非常简单。
而且一旦数据进入到模型，剩下的建模工作都完全一致了。

我们可以使用dataverse数据的实时链接特性在报告中插入powerapps可视化对象来实现数据的实时联动更新：



关键是Dataverse的数据在哪里创建，接下来我们来说这个问题。

1、首先你得有一个Power BI账号，并且得能用Power Apps



2、打开Power Apps，选择“表”：

![image-20220718163045851](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/image-20220718163045851.png)

3、点击新建表：



![image-20220718163148429](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/image-20220718163148429.png)

或者你也可以选择导入表

![image-20220718163745782](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/image-20220718163745782.png)

4、如果选择了新建表，可以设置表的属性及主列

注意显示名为英文或数字

![image-20220718164331042](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/image-20220718164331042.png)

5、添加列和数据

注意列名也需要为英文或数字；并且可以提前设置好数据类型

![image-20220718164733065](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/image-20220718164733065.png)

我们也可以使用其内置的数据，比如创建者和日期、修改者和日期等。

![image-20220718165406379](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/image-20220718165406379.png)

然后我们可以输入一些数据。随时输入和修改，随时自动保存的。

![image-20220718165553263](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/image-20220718165553263.png)

当然，我们也可以根据此数据创建一个power apps应用，来达到数据的实时操作更新的目的。



甚至，我们可以继续发挥想象，使用power automate，结合power bi最新的execute query去实现一些power bi报告中某些特定的时间节点的记录回写，甚至改写。

对于power bi报告的评论系统我们现在可以有更好的解决方案。

总之，发挥想象就好了。

![image-20220718174252796](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/image-20220718174252796.png)

只不过，需要使用这些功能，需要高级版账号才可以。

![image-20220718174708767](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/image-20220718174708767.png)