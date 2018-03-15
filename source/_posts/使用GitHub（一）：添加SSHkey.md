---
title: 使用GitHub（一）：添加SSHkey
date: 2018-03-15 19:36:15
tags:
---
# 使用GitHub（一）：添加SSHkey

>  -  本文简单介绍使用GitHub对代码进行版本控制，包括**添加SSHkey**、**配置Git**、**使用Git创建版本库**并在GitHub上进行管理，主要目的是对学习内容进行总结以及方便日后查阅。
>  - 详细教程和原理可以参考[廖雪峰的Git教程](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)或[猴子都能看懂的Git教程](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)。
>  - 本文版权归马涛涛所有。
>  - 本文所引用的图片和文字版权归原作者所有，侵权删。
>  - 如有错误请在下方评论区指出，欢迎积极讨论。


----------


## 添加SSHkey

>  - 简单说，SSH是一种**网络协议**，用于计算机之间的**加密登录**。
>  - 如果一个用户从本地计算机，**使用SSH**协议登录另一台远程计算机，我们就可以认为，这种登录是**安全**的，即使被中途截获，密码也不会泄露。
>  - 最早的时候，互联网通信都是明文通信，一旦被截获，内容就暴露无疑。1995年，芬兰学者TatuYlonen设计了SSH协议，将**登录信息全部加密**，成为互联网安全的一个基本解决方案，迅速在全世界获得推广，目前已经成为Linux系统的标准配置。
>  - 在这里你只需要知道使用GitHub之前需要添加SSHkey，用来验证GitHub远程仓库就可以了，如果想深入了解原理，参考[阮一峰SSH原理][1]。

步骤：

 1. 进入 https://github.com/settings/keys
 2. 如果页面里已经有一些 key，就点「delete」按钮把这些 key 全删掉。如果没有，就往下看
 ![参考示例][2]
 3. 点击 New SSH key，你需要输入 Title 和 Key，但是你现在没有 key，往下看
 > 添加步骤参考[这里][3]
 4. 打开 Git Bash
 5. 复制并运行 `rm -rf ~/.ssh/*` 把现有的 ssh key都删掉，这句命令行如果你多打一个空格，可能就要重装系统了，建议复制运行。
 6. 运行 `ssh-keygen -t rsa -b 4096 -C "你的邮箱"`，注意填写你的真实邮箱。
 7. 按回车三次
 参考示例：![参考示例][4]
这时会在~目录下生成一个.ssh的隐藏文件 ![参考示例2][5]
 8. 运行 `cat ~/.ssh/id_rsa.pub`，得到一串东西，完整的复制这串东西
 9. 回到上面第 3 步的页面，在 Title 输入「我的第一个 key」
 10. 在 Key 里粘贴刚刚你你复制的那串东西
 ![复制key][6]
 11. 点击 Add SSH key
 12. 回到 Git Bash
 13. 运行 `ssh -T git@github.com`，你可能会看到这样的提示：
 ![提示](http://upload-images.jianshu.io/upload_images/11017215-930bc23329e6f29e..png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
 
 14. 输入 `yes` 回车
 15. 然后如果你看到 `Permission denied (publickey).` 就说明你失败了，请回到第 1 步重来，是的，回到第 1步重来；如果你看到 `Hi FrankFang! You've successfully authenticated, but GitHub does not provide shell access.`
 
![成功示例][7]

 就说明你成功了！
 16. 好了， 添加了一SSH key，接下来就会用到它。



>  - 一台电脑只需要一个 SSH key
>  - 一个 SSH key 可以访问你的所有仓库，即使你有 1000000 个仓库，都没问题
>  - 如果你新买了电脑，就在新电脑上重新生成一个 SSH key，把这个 key 也上传到 GitHub，它可以和之前的 key 共存在    GitHub 上
>  - 如果你把 key 从电脑上删除了，重新生成一个 key 即可，替换之前的 key


  [1]: %EF%BC%88https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/%EF%BC%89
  [2]: https://s1.ax1x.com/2018/03/15/94Niz8.png
  [3]: https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/
  [4]: https://s1.ax1x.com/2018/03/15/94NAsg.png
  [5]: https://s1.ax1x.com/2018/03/15/94NELQ.png
  [6]: https://s1.ax1x.com/2018/03/15/94NZZj.png
  [7]: https://s1.ax1x.com/2018/03/15/94Nuiq.png