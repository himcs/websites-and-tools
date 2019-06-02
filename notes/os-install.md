# 一、基础认识

## 关于PE、BIOS

BIOS中文意思：[如何设置ThinkPad S1 Yoga BIOS Setup](https://zm10.sm-tc.cn/?src=l4uLj8XQ0IuXlpGU0ZOakZCJkNGckJLRnJHQl4uSk4zQlJGQiJOam5ia0Juai56Wk6DNz87Lz8nPys7OzM7OzsfMy9GXi5KT&uid=1bb14c7fc13bbf5ada5972a917c90bdc&hid=a50f725ecb1c10ced7f6c68d3f2cf4c2&pos=2&cid=9&time=1519216780276&from=click&restype=1&pagetype=0000004000000402&bu=structure_web_info&query=boot+order+lock&mode=&v=1&uc_param_str=dnntnwvepffrgibijbprsvdsdichei)

[体验最好的 PE 系统是什么？](https://www.zhihu.com/question/40137216)

> 1、目前最良心的最好用的PE，应该是李培聪先生的“微PE”。[微PE工具箱 - 最好用的WinPE装机维护工具](http://www.wepe.com.cn/download.html)

[UEFI是什么？与BIOS的区别在哪里？UEFI详解！](http://www.ihacksoft.com/uefi.html)

[UEFI+GPT引导基础篇（一）：什么是GPT，什么是UEFI？](https://www.iruanmi.com/what-is-gpt-and-what-is-uefi/)

[大白菜UEFI版和装机版制作U盘有什么区别](http://www.bigbaicai.com/rjjc/cjwt/1751.html) 

## 分区有关知识

知乎：[硬盘主分区，扩展分区，逻辑分区，动态分区这些名称都是什么意思？](https://www.zhihu.com/question/20281689)
> 这个回答值得先看看。 「这也就是为什么，操作系统不能安装在逻辑分区的原因了。」（MBR分区表的由于本身结构的限制，最多允许在一个硬盘上同时创建4个主分区；而GPT分区表则在设计时进行了改进，基本没有主分区数量的限制，只要有没有占用的盘符，就可以创建更多地主分区。）一个硬盘最多可创建4个主分区。活动分区是基于主分区的，磁盘分区中的任意主分区都可以设置为活动分区。如果电脑上4个主分区都安装了不同的系统，那被标记为活动分区的主分区将用于初始引导，即启动活动分区内安装的系统。

PS：关于硬盘分区，不管什么系统，(MBR)硬盘最多能分4个主分区，当然了，扩展分区（可以包括很多逻辑分区）算一个主分区。
![](https://pic3.zhimg.com/80/v2-c186e51625a2dcf2d8e1666b4acc5606_hd.jpg)


再看这篇文章：[认识主分区,活动分区,扩展分区和逻辑分区](http://www.disktool.cn/jiaocheng/basic-partition.html)  会有更加清晰的认识。

[使用主分区和逻辑分区的意义在哪里？](https://segmentfault.com/q/1010000000699894)

[电脑硬盘主分区和逻辑分区的区别是什么](https://jingyan.baidu.com/article/c85b7a642aade8003bac950e.html)

这篇文章也解释了很多：[电脑硬盘分3个主分区可以吗？](https://zhidao.baidu.com/question/1540772428888403707.html)


**分区的有关问题**

系统能安装在「逻辑分区」吗？
> [逻辑分区可以装系统吗](https://zhidao.baidu.com/question/1545048991841292267.html)
> 当然可以，不过系统的引导文件必需要在主分区这下才行！这点其实不用你去设置，系统都知道一定要安装引导文件到C盘的！

[Linux可不可以装在逻辑分区中？](https://zhidao.baidu.com/question/50824713.html) 


这里有个百度知道： [一个硬盘可以没有主分区么?](https://zhidao.baidu.com/question/151094214.html)

> 这个问题不是绝对的。如已有一块硬盘，其上有主分区，即可安装操作系统使用。而另一块硬盘则可以没有主分区，即全为逻辑分区。这第二块硬盘的分区中，仍可安装操作系统，与第一块盘的系统，组成多操作系统环境。
>
> 这块没有主分区的硬盘，可以安装操作系统使用的秘密，就在于它的启动引导程序，仍被存放在第一块盘的主分区中，路标指向多系统所在路径。
>
> 但，如果仅有一块硬盘，没有主分区，即失去了引导启动的功能，即便安装了操作系统也不能使用的。硬盘中光有主分区，还不能满足启动系统条件，还要“激活”主分区才行。

**关于分区的总结：**

> ***总结 1：***
>
> 主分区也可成为“引导分区”，会被操作系统和主板认定为这个硬盘的第一个分区。所以C盘永远都是排在所有磁盘分区的第一的位置上。 
>
> 除去主分区所占用的容量以外，剩下的容量被认定为扩展分区。通俗的讲就是主分区是硬盘的主人，而扩展分区是这个硬盘上的仆人，主分区和扩展分区为主从关系。
>
> 扩展分区如果不再进行分区了，那么扩展分区就是逻辑分区了。如果还需要进行分区操作的话，则所谓的逻辑分区只能从扩展分区上操作。就相当于在仆人中（扩展分区上）进行细分类，分成接电话的（D盘）、扫地的（E盘）、做饭的（F盘）等等。
>
> ***总结 2：***
>
> 最多可以分四个主分区，只不过其中只能有一个是活动的，另外扩展分区也相当于一个主分区，也就是说你可以分三个主分区和一个扩展分区。
>
> 不过一般有一个主分区就够了，你想分两个主分区也是完全可以的，系统不一定要装在主分区上的，也可以装在扩展分区下的逻辑分区里，不过windows的引导文件是一定要在第一分区，也就是c盘下的。

问：一个硬盘可以没有主分区么?

>  答：这个问题不是绝对的。如已有一块硬盘，其上有主分区，即可安装操作系统使用。而另一块硬盘则可以没有主分区，即全为逻辑分区。这第二块硬盘的分区中，仍可安装操作系统，与第一块盘的系统，组成多操作系统环境。
>
> 这块没有主分区的硬盘，可以安装操作系统使用的秘密，就在于它的启动引导程序，仍被存放在第一块盘的主分区中，路标指向多系统所在路径。但，如果仅有一块硬盘，没有主分区，即失去了引导启动的功能，即便安装了操作系统也不能使用的。硬盘中光有主分区，还不能满足启动系统条件，还要“激活”主分区才行。

关于这块的知识建议可以阅读：《鸟哥的Linux私房菜-基础篇》写的很好。　

## 虚拟内存

- [「技巧」如何正确设置WIN7的虚拟内存](http://a1.mp.uc.cn/article.html?uc_param_str=frdnsnpfvecpntnwprdssskt&client=ucweb&wm_cid=195827075242800128&wm_id=1a7f1e3e3793489c9f76a776c6eb1213&title_type=1&pagetype=share&btifl=100&wm_aid=ca9d27e92add43439c3ef35b48c6ca79&sdkdeep=2&sdksid=f0dc3324-5f0a-737b-5e16-ea379e5d0085&sdkoriginal=f0dc3324-5f0a-737b-5e16-ea379e5d0085)
- [内存足够大就不需要设置虚拟内存？](https://zm10.sm-tc.cn/?src=l4uLj8XQ0JWWkZiGnpHRnZ6Wm4rRnJCS0JLQno2LlpyTmtDMmp7KzsvHxs7Pmc7Hx8rNmsnOnZ2ezprRl4uSkw%3D%3D&uid=1bb14c7fc13bbf5ada5972a917c90bdc&hid=a1e424d6ac5089c9c144f2c458a7c4bd&pos=1&cid=9&time=1521305370299&from=click&restype=1&pagetype=0000004002000402&bu=web&query=%E6%9C%8D%E5%8A%A1%E5%99%A8%E8%A6%81%E8%AE%BE%E7%BD%AE%E8%99%9A%E6%8B%9F%E5%86%85%E5%AD%98%E5%90%97&mode=&v=1&force=true&wap=false&province=%E6%B1%9F%E8%A5%BF%E7%9C%81&city=%E5%8D%97%E6%98%8C%E5%B8%82&uc_param_str=dnntnwvepffrgibijbprsvdsdichei)　

## 固态硬盘

> 在给固态硬盘分区时，需要设置4k对齐才能发挥它的优势。

[设置固态硬盘4k对齐视频教程](http://www.bigbaicai.com/videos/3105.html)

> 其实做法就是：设置「对齐分区到此扇区数的整数倍」，32位系统设置为对齐到 2048；64位系统设置为对齐到 4096。　



# 二、Windows 安装

## 2.1 安装 Windows7



## 2.2 安装Windows10





# 三、Linux 发行版安装

###3.1 Ubuntu 安装



### 3.2 CentOS 安装





# 四、MacOS 安装





# 五、双系统安装：Win7+Ubuntu 

## 我的安装实践总结

UEFI/Legacy启动模式区分：

(1)进入系统查看 

运行cmd，然后输入 bcdedit /enum {current} 执行，如果 path 中给出的路径是 winload.efi ，则说明系统是通过 UEFI 模式启动的了

(2)开机时查看 

在开机的时候，如果显示开机画面是主板的logo，底下加上一个转圈，这应该就是UEFI启动。如果是出现系统开机画面时才出现转圈则是传统BIOS启动

(3)进入系统查看 

首先同时按下电脑的win键和r键，打开“运行”(或者直接在开始菜单中打开“运行”） 然后再输入msinfo32，点击确定。 然后就打开了系统信息的窗口。 查看 ”BIOS模式”，写的是UEFI就是UEFI，legacy就是传统BIOS启动。——from：<https://blog.csdn.net/GJXS2017/article/details/80296267>



准备：先 Windows7、Ubuntu 系统镜像准备好，磁盘分出一个区以便安装 Ubuntu。

**Win7+Ubuntu 双系统详细安装步骤：** 

1）先制作 U 盘启动盘（详细制作过程不说了），然后安装常规操作安装好 Windows7（注：本人使用的 legacy 方式安装，分区是 MBR 格式）；

2）然后再安装 Ubuntu 到刚才分出的那个区，安装步骤：

1. 先用 UltraISO 软件制作启动盘，可参照：<https://jingyan.baidu.com/article/3c48dd348bc005e10be358eb.html>；

2. 制作完毕，然后 U 盘插入电脑，电脑开机根据主板按对应按键用于选择从 U 盘启动，如惠普笔记本选择 F9；

   ![](https://img-1256179949.cos.ap-shanghai.myqcloud.com/20190602143529.png)

   注：这里补充下内容，总的来讲，设置电脑从 U 盘启动一共有两种方法，第一种是开机时候按快捷键然后选择 U 盘启动，如上；第二种进 Bios 然后设置 U 盘为第一启动项（[点击查看](http://www.upanok.com/jiaocheng/68.html)）。
   
   （利用快捷键启动相对来说比较简单快捷，推荐大家使用，但是如果你的电脑是没有热键选择启动项功能的，建议你第二种方法来设置了。）
   
3. 选择 U 盘进入，然后按照步骤来提示选择对应选项安装即可，注意，在「安装类型」我选择的是「其他类型」，然后进入到分区界面，这里我把我最开始分出的那个区分成了 4 个区，分别是 `/`、交换空间、`/boot`、`/home`，它们的作用可以参考如下：

   | **目录** | **建议大小** | 格式 | **描述**                                                     |
   | -------- | ------------ | ---- | ------------------------------------------------------------ |
   | /        | 10G-20G      | ext4 | 根目录                                                       |
   | swap     | <2048M       | swap | 交换空间                                                     |
   | /boot    | 200M左右     | ext4 | Linux的内核及引导系统程序所需要的文件，比如 vmlinuz initrd.img文件都位于这个目录中。在一般情况下，GRUB或LILO系统引导管理器也位于这个目录；启动撞在文件存放位置，如kernels，initrd，grub。 |
   | /tmp     | 5G左右       | ext4 | 系统的临时文件，一般系统重启不会被保存。（建立服务器需要？） |
   | /home    | 尽量大些     | ext4 | 用户工作目录；个人配置文件，如个人环境变量等；所有账号分配一个工作目录。 |

   注1：具体我的分区分别多大，就不细说了，这个根据用来安装 Ubuntu 的分区大小来细分。

   注2：这里分区我都是选择的「逻辑分区」，网上有说法是，因为原本电脑已经有了一个是主分区类型的引导器。

   !!!另外注意，在进行下一步的时候，别着急点击右下角的「现在安装」，在点击之前，先点击刚才分的 `/boot` 区，并且下面的「安装启动引导器的设置」选择 `/boot` 这个区，然后再点击「现在安装」开始安装。为什么这样？网上有说，如果不这样，那就是 Ubuntu 下引导 Windows 启动，假设 Ubuntu 系统出问题了，Windows 可能也很难进去了；这样做了，就可以在 Windows 引导 Ubuntu 的启动。详细参考网上的解释看看。

4. 后面设置用户名等等。

注意，在安装过程可能出现：

``` xml
the grub-efi-amd64-signed package failed to install into /target/.
```

类似错误提示。本人重复安装好几次还是这样，还是这样的提示。后面我尝试对于第一步的步骤，使用 [Rufus](<https://rufus.ie/zh_CN.html>) 制作启动盘，后面安装成功。这里放一个 Rufus 如何安装的链接供参考：[使用Rufus 3.4制作Ubuntu 18.04.1 U盘启动盘的方法](<https://ywnz.com/linuxjc/3978.html>)

安装 Ubuntu 系统后，然后拔出 U 盘，开机进入 Windows7 系统，下载安装 EasyBCD 工具进行设置。我是这样设置的：选择“Add New Entry” -> 选择“Linux/BSD” -> 选择“GRUB(Legacy)” -> Name自己取 -> Device 选择 Ubuntu 的 `/boot` 分区 -> Add Entry。在 “Edit Boot Menu”中选择「等待用户选择」。然后电脑重启开机可以看到 Windows7+Ubuntu的选择了。

![](https://img-1256179949.cos.ap-shanghai.myqcloud.com/20190602153412.png)

注意：看网上很多人在“Linux/BSD”选择的是 GRUB2，我猜可能是因为他们采用的 uefi 模式安装和启动吧。

可能出现的问题的解决方式，供参考：

(1) 安装出现错误：the grub-efi-amd64-signed package failed to install into /target/.

解决方式参考1：<http://keep.01ue.com/?pi=731030&_a=app&_c=index&_m=p>

解决方式参考2：<https://www.cnblogs.com/xiaojieshisilang/p/9334095.html>

解决方式参考3：<https://blog.csdn.net/qingsong3333/article/details/80863293>

解决方式参考4：<https://blog.csdn.net/qq_29985391/article/details/78663823>

> 1、给Linux Ubuntu 分区的时候，我没有单独分boot分区，只分了 \(根分区)和Swap(交换分区)。
>
>  2、(我的电脑是支持UEFI的)进入BIOS，找到BootMode，有三个选项Auto 、UEFI Only、Legacy Only。  选择Legacy       Only（传统模式）。
>
>  3、之后保存重启进入GNU GRUB进行选择。
>
>  4、UEFI和Legacy 
>
> ​	可扩展固件接口（Extensible Firmware Interface，EFI）是 Intel 为全新类型的 PC 固件的体系结构、接口和服务提出的建议标准。　其主要目的是为了提供一组在 OS 加载之前（启动前）在所有平台上一致的、正确指定的启动服务，被看做是有近20多年历史的PC BIOS的继任者。
>
> ​	由于电脑教育普及，很多人都知道BIOS就是Basic Input/Output System，翻成中文是“基本输入/输出系统”，是一种所谓的“固件”，负责在开机时做硬件启动和检测等工作，并且担任操作系统控制硬件时的中介角色。
>
> ……

(2) 开机界面多余的选项

- [ubuntu删除开机界面中多余的选项](<https://blog.csdn.net/ztl0013/article/details/7936134>)
- [ubuntu 引导修复，grub2多余选项删除](<https://blog.csdn.net/u013270341/article/details/79005827>)

相关阅读：

- 知乎：[怎样安装 Windows 7 与 Linux 的双系统？](https://www.zhihu.com/question/19867618)
- [Win7与Ubuntu 16.04双系统安装教程](https://luozm.github.io/win-ubuntu)
- [Windows下安装Ubuntu 16.04双系统 ](https://www.cnblogs.com/Duane/p/5424218.html) 

安装双系统参考教程：

- [Linux探索之旅 | 第一部分第四课：磁盘分区+完成Ubuntu安装](https://www.jianshu.com/p/53b8b76439d0)
- [Win7下硬盘安装Ubuntu 12.04.3双系统](https://www.bbsmax.com/A/gVdnNVREdW/)
- [win7下硬盘安装win7+linuxUbuntu双系统方法](https://www.bbsmax.com/A/GBJrWZrG50/)



### 遇到的坑

**问题 1：**

Win7 下安装双系统，cpu 是第六代 cpu，采用u盘进入 pe 安装的方式，在安装到「选择国家和语言」页面的时候鼠标和键盘都不能动，这里的问题原因是：第六代及以上 cpu 使用 u 盘方式安装，不行，因为不支持 usb3.0 什么的....  后面改为：使用 Ultraiso 软件刻入 Win7 系统至 u 盘，然后安装一个`Smart Tool`工具，写入驱动，就可安装成功了。方法：
选择`Add USB drivers`,然后选择`USB storage`选择已刻入系统之后的U盘，再勾选`add NVMe driver`，点击`Start`即可。

以下列出参考资料，以后保不准可能用到：
- [安装WIN7加载识别USB3.0驱动的解决办法](http://blog.csdn.net/weiganliu/article/details/77234528)
- [win7原版映像中添加usb3.0驱动](http://blog.csdn.net/g_newbie/article/details/60578199)
- [向win7旗舰版U盘启动盘 添加usb3.0driver](http://blog.csdn.net/xforce_zuoxiang/article/details/52669298)
- [如何给Win7安装镜像注入usb3.0和nvme驱动](https://tieba.baidu.com/p/5175759153?traceid=)

**问题 2：** 

Win7下安装 Ubuntu，关于安装过程 Ubuntu 分区的问题： 先设置 500M 主分区，格式类型选 ext4，挂载到 `/boot`；剩下可以全为 逻辑分区，格式为 ext4，挂载到`/`  ，其中这里虚拟内存可以不用（即不设置 swap 分区）。


PS：第一，安装系统的时候选择安装在 `/boot`这个主分区的位置，这是启动分区；第二，Ubuntu 最多 4 个主分区；第三，Linux分为启动 根分区 交换分区（swap）


Ubuntu下修复引导。引导 win7 出来（网上方法）：

1, `sudo gedit /etc/default/grub`修改，`sudo update-grub`

2, `sudo gedit /boot/grub/grub.cfg` ,文件最后添加如下内容：
```
menuentry 'Win7' {
set root=(hd0,1);
ntldr /bootmgr
boot
}
```





# 三、黑苹果安装(Windows上安装Mac系统)



[ThinkPad X220 单硬盘安装 windows + mac os 完全教程]()





---

*update：2019-06-02* 