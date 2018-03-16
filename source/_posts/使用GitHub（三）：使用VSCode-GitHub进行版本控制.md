---
title: 使用GitHub（三）：使用VSCode+GitHub进行版本控制
date: 2018-03-16 19:51:29
tags:
---
# 使用GitHub（三）：使用VSCode+GitHub进行版本控制

>  -  本文简单介绍**使用VSCode+GitHub进行项目或者代码的版本控制**。本文主要目的是对学习内容进行总结以及方便日后查阅。
>  - 详细教程和原理可以参考[廖雪峰的Git教程](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)或[猴子都能看懂的Git教程](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)。
>  - 本文版权归马涛涛所有。
>  - 本文所引用的图片和文字版权归原作者所有，侵权删。
>  - 如有错误请在下方评论区指出，欢迎积极讨论。



----------
## 使用原理
----
### 1 上节回顾
上一篇博客详细介绍了**使用 git 的三种方式**

 - 只在本地使用
 - 将本地仓库上传到 GitHub
 - 下载 GitHub 上的仓库

以及**如何上传更新到GitHub**，你在本地目录有任何变动，只需按照以下顺序就能上传：

```
git add 文件路径
git commit -m "信息"
git pull  （一定不要忘记这一个命令）
git push
```

### 2 使用原理

> 本文所写的是使用VSCode中的GitHub功能，可以取代命令行中Git的四步更新的方式，简化上传步骤。

所以**使用VSCode+GitHub进行项目或者代码的版本控制**有以下两种方法：
1. 在本地使用Git仓库→将仓库上传到GitHub→VScode打开→手动进行4步
2. 在GitHub上新建仓库，下载仓库到本地→ VScode打开→手动进行4步

本文只记录**从VScode打开之后**的操作。

## 步骤

1. 使用VSCode打开项目或代码的仓库
    ![打开仓库][1]
2. 点击侧边栏的  **源代码管理**按钮，或者快捷键<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>G</kbd>，这时并没有消息提示。

    ![源代码管理][2]

3. 这时我们新建一个`style_test.css`文件，旁边会出现`U`的符号，意思是更新尚未上传到GitHub

    ![更新][3]

4. 再次打开**源代码管理**，发现多了更新提示。
 ![此处输入图片的描述][4]
 
5. 这时就可以提交更新到GitHub了，作用同命令行中的`git commit -m "new css file"`
 ![此处输入图片的描述][5]

6. 最后一步是pull和push，分别等同于命令行中的`git pull`和`git push`
    ![pullpush][7]

7. 查看GitHub，更新成功
    ![GitHub同步更新][6]



  [1]: https://s1.ax1x.com/2018/03/15/94IWhq.png
  [2]: https://s1.ax1x.com/2018/03/15/94I43V.png
  [3]: https://s1.ax1x.com/2018/03/15/94IxgK.png
  [4]: https://s1.ax1x.com/2018/03/15/94oiEd.png
  [5]: https://s1.ax1x.com/2018/03/15/94oFUA.png
  [6]: https://s1.ax1x.com/2018/03/15/94o8Cq.png
  [7]: https://s1.ax1x.com/2018/03/15/94oQEj.png