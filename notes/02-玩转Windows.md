## Windows 终端

开源地址：<https://github.com/microsoft/terminal>

Win 10 上安装教程：[Windows Terminal微软新版终端工具安装教程（附配置文件）](https://baiyue.one/archives/484.html)  |  视频：[第45期 Windows Terminal微软新版终端工具安装教程](<https://www.bilibili.com/video/av51726432/>)



## windows 常用快捷键

- `Ctrl+R`：打开运行窗口
- `Alt+Tab`：切换窗口
- `Win+X`：打开 Windows 移动中心（可开关无线网络、调节音量、显示器亮度等）
- `Win+D`：回到桌面
- 进入目录，按住 `Shift` 键，再鼠标右键 --> 「在此处打开命令窗口」
- `Win+E`：打开「计算机」
- `Ctrl+W`：关闭窗口（浏览器下也可用。浏览器下新开窗口：`Ctrl+T`）
- `Ctrl+P`：关于与投影仪的连接（断开、复制、扩展、仅投影仪）
- `Win+L`：锁屏



## windows cmd 命令

- `regedit`：打开注册表
- `netstat -ano`：列出所有端口的情况。
  - 若端口占用，可以先在列表中我们观察被占用的端口
- `mstsc`：打开远程桌面连接
- `calc`：打开计算器
- `cls`：清除窗口信息
- `systeminfo`：查看系统的详细状态，除了基本系统信息，还可以查看系统补丁及网络信息和 CPU 主板等信息
- `shutdown -s -t 30`：电脑倒计时，将会在 30 秒后关机
- `msconfig`：是 Microsoft System Configuration 的缩写。在开始菜单里运行中输入然后确认就可以找到程序开启或者禁用，可以帮助电脑禁止不需要运行的程序，这样可以加快你的电脑运行。
- 



## windows 使用技巧

### Windows 常见设置

(1) 在 Windows 文件管理器中，输入`%APPDATA%`,回车，进入电脑`...\AppData\Roaming`目录。

(2) 设置 Windows 软件开机自启：
1. 打开路径`C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Startup`，即打开`程序——>启动`，或者 CMD 下运行：`shell:startup`打开；
2. 将需要开机自动启动的软件的快捷方式粘贴到“系统启动文件夹”里。

(3) Win7 怎么关闭自动锁屏？

1. 控件面板--网络和INTERNET--网络和共享中心--更改适配器设置--本地连接（右击）--属性--配置--电源管理
   把关闭此电源已节约电的勾去掉，这样就可以解除锁定计算机，避免出现锁定后断网的现象。
2. 开始 –> 控制面板 –> 电源选项  –> 更改计划设置 –> 使计算机进入睡眠状态，设成从不 –> 保存修改 
3. 右击桌面 –> 个性化 –> 屏幕保护程序 –> 设置等待时间长一点或者屏幕保护程序为无就行了
4. 不行的话，屏幕保护程序下面那里有一个更改电源设置。打开之后按照以下的设置。单击更改计算机的睡眠时间，关闭显示器和使计算机进入睡眠状态都设置为从不。

### 两台电脑如何连接？

#### 1. windows 访问远程共享(包括连接其他电脑的共享打印机)

Windows 下，`Ctrl+R`，输入 `\\192.168.x.x` 即可访问局域网的远程共享文件，包括局域网其他电脑的共享打印机。

- 连接局域网其他电脑共享的打印机设置：[如何连接其他电脑共享的打印机_百度经验](<https://jingyan.baidu.com/article/f54ae2fcd41fb41e92b849f9.html>)

其他命令：

- `net use`：可看到当前所有的远程访问记录
- `net use * /d`：删除所有访问记录，提示是否删除时，输入y

#### 2. windows “远程桌面 mstsc” 连接局域网其他电脑

`Ctrl+R` 或 `Win` 键，输入`mstsc` 打开“远程桌面”，输入 ip 地址连接即可，前提被连接电脑已设置允许连接。

#### 3. 使用软件远程连接，如 Teamviewer



 



---

*update：2019-05-21* 

