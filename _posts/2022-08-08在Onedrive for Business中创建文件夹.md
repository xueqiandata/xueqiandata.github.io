# 在Onedrive for Business中创建文件夹

在Onedrive for Business（以下简称ODB）中创建一个文件是非常轻松的一件事：

![Untitled](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/Untitled.png)

选择想要的路径，设置文件名，选择文件内容（文件内容大部分时候都是来自于其他action，比如邮件附件或者forms附件等，这里为了简化流程，随便写了一个）：

![Untitled](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/Untitled%201.png)

点击运行，就可以在文件夹中找到这个文件：

![Untitled](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/Untitled%202.png)

但是，如果我们想要创建一个文件夹呢？

好像并没有这么一个action。

不过，在测试的时候我们发现一个问题。如果创建文件时，输入的路径实际并不存在，那么它会自动生成这个路径。比如我们在文件夹路径的后边继续输入“/测试生成路径”：

![Untitled](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/Untitled%203.png)

结果它也照样生成了这个文件，并且还为我们创建了一个新的文件夹：

![Untitled](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/Untitled%204.png)

答案呼之欲出了：

我们将这个a.txt文件删掉，不就达到了创建一个空文件夹的目的了吗？

添加一个ODB的删除文件，选择上一步生成文件的ID：

![Untitled](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/Untitled%205.png)

在ODB中查看，果然生成了一个空文件夹。

![Untitled](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/Untitled%206.png)

我们再看一眼所需的时间，只需要14ms，根本忽略不计。

![Untitled](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/Untitled%207.png)

结论：

Power Automate flow虽然并没有给我们提供一个单独的action来实现在ODB中创建空白文件夹，但是我们通过一点小技巧就可以巧妙的实现。

flow是一个逐渐强大的过程，虽然暂时还有很多的毛病，但是已经可以实现将platform和365大部分功能都协调运用起来，相信它会越来越好。

