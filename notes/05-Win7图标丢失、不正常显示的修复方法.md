根据参考 [1] 来修复桌面白图标方法是打开记事本，复制以下内容：

``` markdown
@echo off
taskkill /f /im explorer.exe
CD /d %userprofile%\AppData\Local
DEL IconCache.db /a
start explorer.exe
cho 执行完成
```

保存为后缀 `.bat` 格式文件，然后运行该 bat 文件即可。若运行完成之后出现黑屏，这种正常情况，部分会因重启 `explorer.exe` 失败而不显示内容，所以黑屏，只要在任务管理器中重新加载 `explorer.exe` 即可，或者直接重启电脑即可，不影响解决问题及系统安全。



根据参考资料 [2] 方法步骤如下：

1. 打开任务管理器（任务栏右键，启动任务管理器），结束正在运行的 `explorer.exe` 进程（explorer 是桌面进程，关闭后，你会发现你的桌面没有了，不要紧，解决问题需要）

2. 点击新任务，在打开空格内输入“CMD”，依次执行以下命令：

   ``` markdown
   CD /d %userprofile%\AppData\Local（回车）
   DEL IconCache.db /a（回车）
   exit（回车）
   ```

   然后重新运行 `explorer.exe`（点击任务管理器的“文件” –> 新建任务“运行”，输入explorer 即可）。

   原理：`IconCache.db` 文件为图标属性文件，由于某种操作，导致文件损坏，删除后，系统会自动重建。然后图标就会恢复正常了。



参考资料：

- \[1] [修复桌面白图标方法，图标有白色的方块怎么办_百度经验](https://jingyan.baidu.com/article/c85b7a64568aac003bac952d.html)
- \[2] [关于Win7图标丢失、不正常显示的修复方法](https://www.cnblogs.com/luckly-hf/p/5135516.html)