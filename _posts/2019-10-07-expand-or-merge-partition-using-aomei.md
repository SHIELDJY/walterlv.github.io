---
title: "使用傲梅分区助手无损合并分区，无损调整分区大小"
date: 2019-10-07 20:14:24 +0800
categories: windows
position: starter
---

Windows 本身就提供了强大的磁盘和分区管理工具，一个是操作简单的“磁盘管理”，一个是功能强大的命令行版的“diskpart”。不过这两个都有一些限制，一是不能影响到系统文件，二是其修改的分区不能被应用程序占用（diskpart 可在下次重启时做到）。另外，系统为了管理工具操作的效率和正确性，也有一些功能没有开放。

DiskGenius 是个强大的工具，不过傲梅也很良心。本文介绍使用傲梅分区助手来管理磁盘。

---

<div id="toc"></div>

## 下载

傲梅分区助手有绿色版、专业版和 PE 版。一般我们选择绿色版就好，如果你要改到系统分区，就需要使用集成了傲梅分区助手的 PE 系统。

- [下载傲梅分区助手](https://www.disktool.cn/download.html)

下面是专业版的截图：

![专业版](/static/posts/2019-10-07-19-53-10.png)

下面是 PE 版的截图，也是我实际操作分区时截下来的图：

![PE 版](/static/posts/2019-10-07-19-54-35.png)

不要吐槽为何我用的是古老的 1709 系统，实际上我的系统盘是下面那个 I 盘。不然为什么我会把系统的版本号放到卷标中呢？

## 调整分区大小

在 PE 系统中找到傲梅分区助手，然后启动。在需要调整位置和大小的分区上右键点击选择“调整/移动分区”：

![调整移动分区](/static/posts/2019-10-07-19-57-11.png)

然后在弹出的详细设置对话框中调整分区的位置和大小。如果是 SSD，建议点击“高级”然后勾选“允许分区对齐以优化SSD或HDD硬盘”，这可以开启 4K 对齐以大幅优化 SSD 的读写性能。

![4K 对齐](/static/posts/2019-10-07-19-58-46.png)

最后点击确定。

注意这个时候还没有开始执行真正的操作！

## 合并分区

合并分区功能可以将你一个磁盘中的多个分区无损合并成一个。

![合并分区](/static/posts/2019-10-07-20-11-15.png)

选择好将哪个分区合并到哪一个，这时另一个分区中的所有文件会放到目标分区中的一个文件夹里。合并完之后你自己移动好这些文件即可。

因为我的分区在合并过程中的操作没有截图，所以只能看到下面这个提前在磁盘管理中的截图：

![无法删除](/static/posts/2019-10-07-10-02-13.png)

## 开始执行真正的操作

在你设置好你的所有操作之后，点击左上角的“提交”按钮，这可以开始依次执行之前所有设置的磁盘最终状态。

![提交](/static/posts/2019-10-07-20-03-24.png)

在提交界面，你可以看到即将进行的所有操作的简介，以及预计完成这些操作所花的时间。

![操作预览](/static/posts/2019-10-07-20-05-48.png)

虽然上图只是示例，但我实际将我在下面这篇博客中删除出来的空余空间全部合并在一起，并且还额外合并了两个都需要保留数据的分区。这个过程傲梅的预计时间是 9小时18分，实际上也刚好在 9 个小时左右！

- [EFI 分区/恢复分区不可删除？你需要使用命令行了（全命令行操作）](https://blog.walterlv.com/post/delete-efi-partition-that-cannot-be-deleted-2.html)

所以，如果你打算开始进行大量的磁盘调整、对拷或者其他**无损分区**操作：

- **请提前准备好大量你不用电脑的时间。**
- **请提前准备好大量你不用电脑的时间。**
- **请提前准备好大量你不用电脑的时间。**

这是我实际上在 PE 中操作的截图：

![分区调整过程](/static/posts/2019-10-07-20-08-33.png)