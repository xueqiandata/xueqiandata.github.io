自从flow的主页改为https://make.powerautomate.com，速度是快了不少，但是好像bug也多了起来。

正常而言，一个action输入框点击之后，可以在表达式的位置进行自定义添加或者修改。

之前一直很正常，但是这两天突然就无法输入了：

![img](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/640)

试了重新登录、更换浏览器、删掉缓存、更换账号、更换网络、更换电脑，一律无法使用。

可能办法真的只剩下一个了，换人。

**经过一番摸索**，发现了如下的解决办法：

比如我的forms表单“商品分类”中的选项格式一般为：“A、黄金叶”，“B、软中华”，我想提取顿号前边的A、B、C这些，正常我应该在表达式中直接写：

```
split(outputs('获取回复详细信息')?['body/rc7dxxxb5'],'、')[0]
```

但是现在没有办法在表达式中直接写，我可以在输入框中

```
@{split(outputs('获取回复详细信息')?['body/rc7dxxxb5'],'、')[0]}
```

即将原本应该写在表达式中的内容，放在@{}里面，然后直接在输入框中粘贴就可以了。

![无法编辑表达式-复制修改](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/%E6%97%A0%E6%B3%95%E7%BC%96%E8%BE%91%E8%A1%A8%E8%BE%BE%E5%BC%8F-%E5%A4%8D%E5%88%B6%E4%BF%AE%E6%94%B9.gif)

**又经过一番摸索**，找到了另一种办法：

点击右上角的齿轮，点击“查看所有设置”

![image-20220725201624797](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/image-20220725201624797.png)

将此处打开，然后保存。

![image-20220725201639806](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/image-20220725201639806.png)

然后就又可以开心地编辑了，只不过显示方式与之前不太一样：

![无法编辑表达式-高级模式](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/%E6%97%A0%E6%B3%95%E7%BC%96%E8%BE%91%E8%A1%A8%E8%BE%BE%E5%BC%8F-%E9%AB%98%E7%BA%A7%E6%A8%A1%E5%BC%8F.gif)



ok！