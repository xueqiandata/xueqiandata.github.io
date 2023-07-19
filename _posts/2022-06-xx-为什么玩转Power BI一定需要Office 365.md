为什么玩转 Power BI 一定需要 Office 365？

BI工具数不胜数，Power BI、Tableau、FineBI、永洪BI、百度智能云等，甚至 python、MATLAB 都可以实现报表功能。

但是为什么 Power BI 能连续15年稳坐 Gartner 魔力象限头把交椅？

![img](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/v2-8e418f97e15d674c07d8564c58839a8a_720w.jpg)



诸多原因。

今天想要阐述的一个观点是：

**正是因为有了 Office 365 这个强大的后盾， Power BI 才会像今天这样受到这么多人的推崇。**

本文主要从以下几个方面阐述：

1、Power BI 从 Onedrive for Business获取文件或文件夹

2、Power BI pbix文件直接从 Onedrive for Business获取并同步

3、Power BI 官方支持嵌入PPT，助力你成为数据演说家

4、Power BI 拥有 Power Automate 的强大加持



## 一、Power BI 从 Onedrive for Business获取文件或文件夹

![image-20220616184636237](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/image-20220616184636237.png)

几乎所有的教程都会告诉你，使用 Power BI 获取数据最简单的方式是从本地excel表中获取，紧接着教你如何从本地文件夹中获取多个文件。

从这一习惯养成的第一天开始，你就为将来某一天的后悔埋下了祸根。

因为不需要太久之后，你就要面临数据刷新、定时刷新、网关配置的问题，此时，如果你看到下面的每一个都需要进行一次凭据的选择：

![image-20220616192831564](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/image-20220616192831564.png)



请问，你作何感想？

尤其是当你每次在本地添加一个新的excel表，保存，发布，等待其自动刷新，但是总是不刷新，找了一圈原因，到数据集这里一看，哦对，需要对新添加的这张表设置凭据。你会不会懊恼不已？

尤其是当你关闭了电脑，你会发现无论如何你是没有办法得到最新的数据的。因为从本地文件获取数据，必须通过网关，而网关必须在开机运行的电脑上。

本地网络出现故障或者网速不给力的情况下，刷新报告是非常漫长的过程，而且经常会报错。

那么，Office 365 可以带给我们什么呢？

使用从 Onedrive for Business 获取文件我们有以下的优势：

![image-20220616151443102](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/image-20220616151443102.png)



①无需手动配置网关。因为数据是云对云，因此本地是否开机，是否联网，网络是否通畅，网速是不是给力毫无影响。而且因为数据都是走的微软服务器，效率也会加倍。

注意：这里使用的是 Onedrive for Business（ODB） ，而不是个人版或家庭版的 Onedrive（OD），因为OD本质上只是个web url，具体参考这篇文章：[【重磅】PowerBI从Onedrive个人版获取文件](https://mp.weixin.qq.com/s/kUuUrhflgYmVYg6KgnToTg)。这里的从ODB获取数据不要求Power BI和ODB为同一个账号或同一个组织账号，但是世纪互联版的 Power BI 无法获取国际版的ODB文件，反之亦然。（特别注意，你可能会登录国际版 Power BI 在本地desktop中尝试获取世纪互联的 ODB 文件成功，但是云端却是无法刷新的，这一点要注意，参考这篇文章的末尾的说明：[针对“PowerBI从Onedrive获取文件”两篇文章做个补充](https://mp.weixin.qq.com/s/TG98cJ5qUQ77ophWU1vEAA)）

②不论从该 ODB 中获取多少个文件或者文件夹，数据源凭证这里永远只有一个，也就说，你只需要在第一次发布报告时配置好，那么以后任何时候再次发布报告，哪怕是发布其他的报告，也都无需再次配置凭据。

③因为有很多公司可能会团队共同维护数据，需要设置共享盘，那么ODB就是一个绝佳的选择，单个用户5T的空间，想必任何数据都可以满足要求。同一个组织内的用户之间通过共享文件和文件夹的方式进行配合实现组织的高效运转。

当然，其实如果你的数据量比较大，还是建议上数据库的。

④ODB中的数据文件，误删或者修改全部都有记录，全都可以随时找回，再也不必担心数据丢失问题。



## 二、Power BI pbix 文件直接从 Onedrive for Business 获取并同步

几乎所有的教程都会告诉你，desktop上制作报告完毕之后，点击发布即可上传到service。如果修改报告，那么只要修改完成后再次点击发布，覆盖原来的云端报告即可。

这很好。但仅限于你没有 Office 365 中的 ODB。

如果你有，那么恭喜你，你解锁了一个**全新的发布报告方式**。

微软官方原话：

[从 Power BI Desktop 文件获取数据 - Power BI | Microsoft Docs](https://docs.microsoft.com/zh-cn/power-bi/connect-data/service-desktop-files)

**OneDrive - 企业** – 如果你有 OneDrive for Business，并且使用登录 Power BI 的同一帐户登录到其中，**这是将 Power BI Desktop 中的工作与你在 Power BI 中的数据集、报表和仪表板保持同步的有史以来最有效的方法**。由于 Power BI 和 OneDrive 都位于云中，Power BI 大约每小时会连接你在 OneDrive 上的文件一次。 如果发现任何更改，你的数据集、报表和仪表板会在 Power BI 中自动更新。



![图片](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/640)

图片来源：PowerBI战友联盟



操作方式：

#### 1、云端工作区中，点击新建-上传文件：

![image-20220616190946094](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/image-20220616190946094.png)

#### 2、点击OneDrive企业版：

![image-20220616191217548](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/image-20220616191217548.png)



#### 3、点击其中的pbix文件：

![image-20220616191311438](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/image-20220616191311438.png)

#### 4、点击右上角连接，即可同时建立数据集、报表和仪表板：

![image-20220616191408860](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/image-20220616191408860.png)



#### 5、点击数据集的三个点-设置：

![image-20220616191553395](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/image-20220616191553395.png)

你的数据集设置里有这个吗？

![image-20220616191651798](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/image-20220616191651798.png)



默认情况下，OneDrive 每小时更新一次文件。

你还在为每天8次定时刷新不知道该怎么设置而苦恼吗？

有了 OneDrive 的24次加持，你还有什么可担心的呢？

#### 6、更新数据

本地修改了文件之后，需要做什么吗？

不需要做任何事情，这一切，交给 OneDrive 和 Power BI 去做了。一小时更新一次，等待即可。

如果不想等？点击“立即刷新”：

![image-20220616192533981](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/image-20220616192533981.png)

你就可以得到最新的模型和数据。

#### 7、团队玩法与个人玩法的不同

你的工作区右侧三个点，里面有**文件**这个选项吗？一定是没有的！

![image-20220616193322361](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/image-20220616193322361.png)



这只是团队玩法和个人玩法之间的数不胜数的差异之间的微不足道的一个。

更多企业级应用分享，请持续关注学谦公众号。企业级应用配置，直接联系学谦沟通。

#### 8、小结

从ODB中获取pbix文件的优势不仅限于如此，假如你有多个工作区，都使用同一个pbix文件中的数据集，进而各自开发报告，如果你是总数据集的持有者，请问你是会选择对同一个pbix文件修改之后在多个工作区分别覆盖发布，还是修改之后点击保存关闭，喝个下午茶，等待系统系统更新？想必你一定会做出正确的选择！

甚至更进一步讲，我们可以通过某种设置，在本地报告修改保存关闭后，自动更新数据集，第四部分中将要介绍的Power Automate就可以完美地实现这个功能。



## 三、Power BI 官方支持嵌入PPT，助力你成为数据演说家

官方的说法是：让数据讲故事。

在以往，你可能会选择 Power BI Tiles或者Web Viewer，但都非官方，支持也一般。

现在，你有了一个全新的选择：

#### 1、从PowerPoint中获取 Power BI 插件：

![image-20220616195549669](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/image-20220616195549669.png)



![image-20220616195625042](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/image-20220616195625042.png)



![image-20220616195651755](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/image-20220616195651755.png)

#### 2、在Power BI service中获取链接：

①②③看步骤：

![image-20220616200959834](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/image-20220616200959834.png)

点击复制：

![image-20220616201031411](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/image-20220616201031411.png)



#### 3、粘贴到ppt中：

![image-20220616201841957](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/image-20220616201841957.png)

#### 4、呈现结果：

![image-20220616201912410](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/image-20220616201912410.png)





#### 5、小结

在ppt中嵌入power bi可以实现真正意义上的用数据讲故事。powerbi嵌入PPT不仅仅是powerbi的革命，同时也是ppt的革命。

很多人不清楚powerbi和ppt到底是什么关系，其实把ppt的全称写出来就懂了：
PowerPoint
PowerBI

这关系比作王中军和王中磊不过分吧。

**前提：登录powerbi的账号和登录office365的账号必须是同一个账号或者同一个组织下的。**



## 四、Power BI 拥有 Power Automate 的强大加持

关于 Power Automate 和 Power BI 的强大联合应用，之前也说过不少了，大家可以直接参考下列的文章：



基础的flow是免费的的，但是高级账号还是需要 Office 365 的加持。





## 总结

总之， Power BI 是强大的，然而在 Office 365 的加持之下，它，更加强大！

你需要有和你的 Power BI 账号是同一个账号或者同一个域名下的 Office 365 企业级权限账号来实现这一切。

至于价格：

![image-20220616205056758](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/image-20220616205056758.png)



可以考虑完全使用官网的正版。也可以联系学谦搞定这一切。