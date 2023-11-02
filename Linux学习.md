

# 第一章：linux入门

## 1.1概述

Linux是一种开源的操作系统，它基于Unix的设计原则。它具有高度的可定制性和灵活性，可以在各种设备上运行，包括个人计算机、服务器、移动设备和嵌入式系统。Linux操作系统由内核和各种工具和应用程序组成，它们一起提供了一个完整的操作环境。Linux操作系统以其稳定性、安全性和可靠性而闻名，并且被广泛用于各种领域，包括科学研究、服务器管理和个人计算机操作系统。

## 1.2 linux和windows区别

![image-20230828213546487](C:\Users\张吉勇\AppData\Roaming\Typora\typora-user-images\image-20230828213546487.png)

## 1.3 Linux下载网址

[centos-7-isos-x86_64安装包下载_开源镜像站-阿里云 (aliyun.com)](http://mirrors.aliyun.com/centos/7/isos/x86_64/)

# 第二章：Vm与linux的安装

Vmware下载：[Windows 虚拟机 | Workstation Pro | VMware | CN](https://www.vmware.com/cn/products/workstation-pro.html)

# 第三章：Linux文件和目录结构

### 3.1 基本介绍

* Linux的文件系统采用级层式子的树状目录结构，
* 最上层是根目录“/”
* **Linux世界里，一切皆文件。**
  ![目录结构](https://i0.hdslb.com/bfs/album/9b6a7fb1fdb9796228fec46327ff0b69953ccaf0.jpg)

## 3.2各目录的作用

* `/bin：` 是Binary的缩写，这个目录存放着最经常使用的命令。
* /sbin：s就是Super User的意思，这里存放的是系统管理员使用的系统管理程序。
* `/home：`存放普通用户的主目录，在Linux中每个用户都有一个自己的目录，一般该目录名是以用户的账号命名的。
* `/root：`该目录为系统管理员，也称作超级权限者的用户主目录。
* /lib：系统开机所需要最基本的动态连接共享库，其作用类似于Windows里的DLL文件。几乎所有的应用程序都需要用到这些共享库。
* /lost+found：这个目录一般情况下是空的，当系统非法关机后，这里就存放了一些文件。
* /etc：所有的系统管理所需要的配置文件和子目录my.conf。
* `/usr/local`：这是一个非常重要的目录，用户的很多应用程序和文件都放在这个目录下，类似与windows下的program files目录。
* `/boot：`存放的是启动Linux时使用的一些核心文件，包括一些连接文件以及镜像文件。
* /proc：这个目录是一个虚拟的目录，它是系统内存的映射，访问这个目录来获取系统信息。
* /srv：service的缩写，该目录存放一些服务启动之后需要提供的数据。
* /sys：这是linux2.6内核的一个很大的变化。该目录下安装了2.6内核中新出现的一个文件系统sysfs。
* /tmp：这个目录是用来存放一些临时文件的。
* /dev：类似windows的设备管理器，把所有的硬件用文件的形式存储。
* `/media：`linux系统会自动识别一些设备，例如U盘光驱等等，当识别后，linux会把识别的设备挂载到这个目录下。
* `/mnt：`系统提供该目录是为了让用户临时挂载别的文件系统的，我们可以将外部的存储挂载在/mnt/上，然后进入该目录就可以查看里面的内容了。
* `/opt：`这是给主机额外安装软件所摆放的目录，如安装ORACLE数据库就可放到该目录下。默认为空。
* /usr/local：这是另一个给主机额外安装软件所安装的目录，一般是通过编译源码的方式安装的程序。
* `/var：`这个目录中存放着在不断扩充着的东西，习惯将经常被修改的目录放在这个目录下，包括各种日志文件。
* /selinux：SELinux是一种安全子系统，它能控制程序只能访问特定文件。

# 第四章：VIm|VM编辑器

## 4.1 是什么

VI 是 Unix 操作系统和类 Unix 操作系统中最通用的文本编辑器。

 VIM 编辑器是从 VI 发展出来的一个性能更强大的文本编辑器。可以主动的以字体颜 色辨别语法的正确性，方便程序设计。VIM 与 VI 编辑器完全兼

## 4.2 VIM的三种模式

### 4.2.1 默认模式

以 vi 打开一个档案就直接进入一般模式了（这是默认的模式）。在这个模式中， 你可 以使用『上下左右』按键来移动光标，你可以使用『删除字符』或『删除整行』来处理档 案内容， 也可以使用『复制、粘贴』来处理你的文件数据。

**操作指令：**![image-20230828215149186](C:\Users\张吉勇\AppData\Roaming\Typora\typora-user-images\image-20230828215149186.png)

### 4.2.2 编辑模式

1. 进入方法和作用：在一般模式中可以进行删除、复制、粘贴等的动作，但是却无法编辑文件内容的！要 等到你按下『i, I, o, O, a, A』等任何一个字母之后才会进入编辑模式
2. 退出方法：按ESC

### 4.2.3 指令模式

1. 在一般模式当中，输入 `: / ?`3个中的任何一个按钮，就可以将光标移动到最底下那 一行。 在这个模式当中， 可以提供你『搜寻资料』的动作，而读取、存盘、大量取代字符、 离开 vi 、显示行号等动作是在此模式中达成的
2. 基本语法

![image-20230828215537434](C:\Users\张吉勇\AppData\Roaming\Typora\typora-user-images\image-20230828215537434.png)

3.强制保存并退出： `:wq`

4.模式间的切换：![image-20230828215713371](C:\Users\张吉勇\AppData\Roaming\Typora\typora-user-images\image-20230828215713371.png)

# 第五章：网络配置（重点）

## 5.1 查看网络ip和网关

![image-20230828220006804](C:\Users\张吉勇\AppData\Roaming\Typora\typora-user-images\image-20230828220006804.png)

## 5.2 三种网络模式

1. **Bridged（桥接模式）**：桥接模式下与主机共用网卡，这样会暴露ip（不建议使用）
2. **NAT（网络地址转换模式）**：主机和虚拟机之间由一个虚拟路由器来进行访问，这就是为什么虚拟机和主机子网掩码不一样，这样由虚拟机访问外网时，虚拟路由器会将需要访问的网关ip传到连接到主机的路由器从而访问外网，而主机为了也可以访问虚拟机，所以也家里一个虚拟的交换机，也就是**VMware Virtual Ethernet Adapter for VMnet8**这个网络，直接连接虚拟机，所以这个网络和虚拟机在一个局域网内
3. **Host-Only（仅主机模式）**

## 5.3 查看虚拟机网络以及配置虚拟机网络ip的各种指令

1. 查看虚拟机网络配置 `ifconfig`，查看windows网络配置：ipconfig

2. 查看两个主机连通性：**ping**命令

3. 配置网络为静待网络的方法：这个配置文件在  **/etc/sysconfig/network-scripts/ifcfg-ens33**  文件下，使用`vim /etc/sysconfig/network-scripts/ifcfg-ens33`指令，将`BOOTPROTO="dhcp"`改为`BOOTPROTO="static"`，然后后面加上

   ```cmd
   #IP 地址
   IPADDR=192.168.124.129
   #网关
   GATEWAY=192.168.124.2
   #域名解析器
   DNS1=8.8.8.8
   NETMASK=255.255.255.0
   ```
   
   

## 5.4 配置ip时遇到的问题

（1）物理机能 ping 通虚拟机，但是虚拟机 ping 不通物理机,一般都是因为物理机的 防火墙问题,把防火墙关闭就行 

（2）虚拟机能 Ping 通物理机,但是虚拟机 Ping 不通外网,一般都是因为 DNS 的设置有 问题 

（3）虚拟机 Ping www.baidu.com 显示域名未知等信息,一般查看 GATEWAY 和 DNS 设 置是否正确 

（4）如果以上全部设置完还是不行，需要关闭 NetworkManager 服务  systemctl stop NetworkManager 关闭  systemctl disable NetworkManager 禁用

 （5）如果检查发现 systemctl status network 有问题 需要检查 ifcfg-ens3

# 5.5 配置主机名字

1. 查看主机名命令：`hostname`
2. 主机名所在文件夹：`/etc/hostname`修改完成后重启生效，如果需要立即生效用`hostnamectl set-hostname dselegent-study【要修改的主机名】`命令

## 5.6 设置hosts映射文件

1. 文件位置：/etc/hosts ,使用`vim /etc/hosts`命令添加ip和映射名字，如

   ```cmd
   192.168.2.100 ds100
   192.168.2.101 ds101
   192.168.2.102 ds102
   192.168.2.103 ds103
   192.168.2.104 ds104
   192.168.2.105 ds105
   ```

2. 在主机上的**C:\Windows\System32\drivers\etc**目录下的hosts文件中也加上上述内容，就可以用后面的映射名字ping通

# 第六章：系统管理

## 6.1 Linux 中的进程和服务

计算机中，一个正在执行的程序或命令，被叫做“进程”（process）。 

启动之后一只存在、常驻内存的进程，一般被称作“服务”（service）。

> 详细操作后面说明

## 6.2 systemctl 服务管理

> service 服务管理（CentOS 6 版本-了解）
>
> systemctl （CentOS 7 版本-重点掌握）

CentOS 7使用Systemd管理守护进程。centos7采用 systemd管理，服务独立的运行在内存中，服务响应速度快，但占用更多内存。独立服务的服务启动脚本都在目录 /usr/lib/systemd/system里。Systend的新特性：

- 系统引导时实现服务的并行启动；
- 按需激活进程；
- 系统实现快照；
- 基于依赖关系定义服务的控制逻辑；

  systemctl可用于内省和控制“systemd”系统和服务管理器的状态。centos7.x系统环境下我们经常使用此命令启停服务，实际上此命令除了其他独立服务还有很多其他用途。

查看服务的方法：/etc/init.d/服务名 ,发现只有两个服务保留在 service

```cmd
[root@linux1 ~]# ls /etc/init.d/
functions  netconsole  network  README
```

## 6.3 systemctl （CentOS 7 重点）

1. 基本语法：**start | stop | restart | status** 服务名

2. 经验技巧：查看服务的方法：/usr/lib/systemd/system

3. 操作实例：

   - 查看防火墙服务状态：

     ```
     systemctl status firewalld			
     ```

     

   - 停用防火墙：

     ```
     systemctl stop firewalld
     ```

     

   - 启动防火墙

     ```
     systemctl start firewalld
     ```

   - 重启防火墙

     ```
     systemctl restart  firewalld
     ```

     

## 6.4 systemctl 设置后台服务自启动

### 6.4.1 运行级别

![image-20230829195410616](C:\Users\张吉勇\AppData\Roaming\Typora\typora-user-images\image-20230829195410616.png)

最后简化只需要3，5，因为3和2一样但可以联网，4不用。

**centos7 简化为：**

```
multi-user.target 等价于原运行级别 3（多用户有网，无图形界面）
graphical.target 等价于原运行级别 5（多用户有网，有图形界面）
```

### 6.4.2 查看运行级别

```cmd
[root@linux1 ~]# systemctl get-default 
graphical.target
```

### 6.4.3 修改运行级别

```
systemctl set-default TARGET.target （这里 TARGET 取 multi-user 或者 graphical）
```

### 6.4.4 修改防火墙开启是否自启

1. 设置开机自启：

   ```
   systemctl  enable firewalld
   ```

2. 关闭开机自启：

   ```
   systemctl disable firewalld
   ```

   

## 6.5 关机重启命令

### 6.5.1 基本语法

1. **sync:将数据由内存同步到硬盘**

2. **halt：停机，关比系统，但不断电**

3. **poweroff： 关机，断电**

4. **reboot ：重启， 等同于`shutdown -r now`**

5. **shutdown[选项]时间**

   | 选项 | 功能                       |
   | :--: | :------------------------- |
   |  -H  | 相当于-halt 停机，关闭系统 |
   |  -r  | -r=reboot 重启             |

   | 参数 | 功能                        |
   | ---- | --------------------------- |
   | now  | 立即关机                    |
   | 时间 | 等待多久后关机（单位时min） |

   

Linux 系统中为了提高磁盘的读写效率，对磁盘采取了 “预读迟写”操作方式。当用户 保存文件时，Linux 核心并不一定立即将保存数据写入物理磁盘中，而是将数据保存在缓 冲区中，等缓冲区满时再写入磁盘，这种方式可以极大的提高磁盘写入数据的效率。但是， 也带来了安全隐患，如果数据还未写入磁盘时，系统掉电或者其他严重问题出现，则将导 致数据丢失。使用 sync 指令可以立即将缓冲区的数据写入磁盘

# 第七章 ：常用基本命令（重点）

## 7.1 帮助命令

### 7.1.1 man命令获得帮助命令

1. 基本语法：man [命令或配置文件] （功能描述：获得帮助信息）

2. 显示说明

   |    信息     | 功能                   |
   | :---------: | :--------------------- |
   |    NAME     | 命令的名称和单行描     |
   |  SYNOPSIS   | 怎样使用命令           |
   | DESCRIPTION | 命令功能的深入讨论     |
   |  EXAMPLES   | 怎样使用命令的例子     |
   |  SEE ALSO   | 相关主题（通常是手册页 |

3. 操作实例

   ```cmd
   [root@linux1 ~]# man systemctl
   ```

   

### 7.1.2 help 获得 shell 内置命令的帮助信

一部分基础功能的系统命令是直接内嵌在 shell 中的，系统加载启动之后会随着 shell 一起加载，常驻系统内存中。这部分命令被称为“内置（built-in）命令”；相应的其它命令 被称为“外部命令。

1. 基本语法：help [命令或配置文件]

2. 案例实操：查看cd

   ```cmd
   [root@linux1 ~]# help cd
   ```

3. 如果可以推荐使用   [命令或配置文件]--help，里面有汉化

### 7.1.3 常用快捷键

| 常用快捷键    | 功能                                                         |
| ------------- | ------------------------------------------------------------ |
| ctrl+c        | 停止进程                                                     |
| ctrl+l        | 清屏，等同于clear（实际上只是将以前的命令拉到上面），彻底请屏用：reset |
| 善于用 tab 键 | 提示(更重要的是可以防止敲错）                                |
| 上下键        | 查找执行过的命令                                             |

## 7.2 文件夹目录类

### 7.2.1 pwd显示当前工作目录的绝对路径

`pwd:print working directory` 打印工作目录

```cmd
[root@linux1 ~]# pwd print working directory
/root
```

### 7.2.2 ls列出目录的内容

**ls:list 列出目录内容**

1. 基本语法：ls [选项] [目录或是文件]

2. 选项说明：

   | 选项 | 功能                                                         |
   | ---- | ------------------------------------------------------------ |
   | -a   | 全部的文件，连同隐藏档( 开头为 . 的文件) 一起列出来(常用)    |
   | -l   | 长数据串列出，包含文件的属性与权限等等数据；(常用)等价于“ll” |

3. 显示说明：每行列出的信息依次是： 

   - 文件类型与权限 
   - 链接数 
   - 文件属主 
   - 文件属组 
   - 文件大小用byte 来表示
   -  建立或最近修改的时间 
   - 名字

 4.案例实操：

```cmd
[root@linux1 ~]# ls -al
```

### 7.2.3 cd切换目录

1. 基本语法：cd [参数]

2. 参数说明：

   | 参数        | 功能                                 |
   | ----------- | ------------------------------------ |
   | cd 绝对路径 | 切换路径                             |
   | cd 相对路径 | 切换路径                             |
   | cd ~或者 cd | 回到自己的家目录                     |
   | cd-         | 回到上一次的目录                     |
   | cd..        | 回到上一级目录                       |
   | cd -p       | 跳转到实际物理路径，而非快捷方式路径 |

### 7.2.4 mkdir创建一个目录

mkdir:Make directory 建立目录

1. 基本语法：mkdir [目录名称]

2. 选项说明：

   | 选项 | 功能         |
   | ---- | ------------ |
   | -p   | 创建多级目录 |

3. 创建一个目录：

   ```cmd
   [root@linux1 soft]# mkdir soft
   [root@linux1 soft]# mkdir soft/ee
   ```

4. 创建多级文件夹

   ```cmd
   [root@linux1 soft]# mkdir -p soft/bb
   ```

### 7.2.5 rmdir删除一个空的目录

rmdir:Remove directory

1. 基本语句：rmdir 要删除的空目录
2. 实操：和mkdir一样

### 7.2.6 touch创建一个空文件

1. touch 文件名

2. 实操：

   ```cmd
   [root@linux1 soft]# touch bb/a.test
   ```



### 7.2.7 cp 复制文件或目录

1. cp [选项] source dest （功能描述：复制source文件到dest）

2. 选项说明

   | 选项 | 功能               |
   | ---- | ------------------ |
   | -r   | 递归复制整个文件夹 |

3. 参数说明

   | 参数   | 功能     |
   | ------ | -------- |
   | sourse | 源文件   |
   | dest   | 目标文件 |

4. 经验技巧：强制覆盖不提示的方法：\cp，这样就不要回答yes or no覆盖文件，因为\cp是直接使用的Linux的原生命令,使用后就不加-后面的修饰

   ```cmd
   [root@linux1 soft]# alias
   alias cp='cp -i'
   alias egrep='egrep --color=auto'
   alias fgrep='fgrep --color=auto'
   alias grep='grep --color=auto'
   alias l.='ls -d .* --color=auto'
   alias ll='ls -l --color=auto'
   alias ls='ls --color=auto'
   alias mv='mv -i'
   alias rm='rm -i'
   alias which='alias | /usr/bin/which --tty-only --read-alias --show-dot --show-tilde'
   ```


### 7.2.8 rm 删除文件或目录

1. 基本语法： rm [选项] deleteFile （功能描述：递归删除目录中所有内容）

2. 选项说明：

   | 选项 | 功能                                     |
   | ---- | ---------------------------------------- |
   | -r   | 递归删除目录中的所有内容                 |
   | -f   | 强制执行删除操作，而不提示用于进行确认。 |
   | -v   | 显示指令的详细执行过程                   |

3. 操作实例

   ```cmd
   [root@linux1 module]# rm -r  soft/bb
   rm：是否进入目录"soft/bb"? y
   rm：是否删除普通空文件 "soft/bb/a.test"？y
   rm：是否删除目录 "soft/bb"？y
   ```

   ```cmd
   [root@linux1 module]# rm -rf soft
   ```

### 7.2.9 mv 移动文件与目录或重命名

1. 基本语法：`mv oldNameFile newNameFile` （功能描述：重命名） mv /temp/movefile /targetFolder （功能描述：移动文件）
2. 操作实例   

- 重命名

  ```cmd'
  [root@linux1 software]# mkdir aa
  [root@linux1 software]# ls
  aa
  [root@linux1 software]# mv aa bb
  ```

- 移动文件

  ```cmd
  [root@linux1 software]# touch a.text
  [root@linux1 software]# ls
  a.text
  [root@linux1 software]# mv a.text ../soft/
  ```

### 7.2.10 cat 查看文件内容

查看文件内容，从第一行开始显示。

1. 基本语法 cat [选项] 要查看的文件

2. 说明

   | 选项 | 功能描述                     |
   | ---- | ---------------------------- |
   | -n   | 显示所有行的行号，包括空行。 |

3. 操作实例

   ```cmd
   [root@linux1 soft]# cat -n a.text
        1	dasdadadad
        2	    
        3	dsd
        4	**&* 
        5	fdssa
   ```

4. 经验：一般查看比较小的文件，一屏幕能显示全的。



### 7.2.11 more 文件内容分屏查看器 

more 指令是一个基于 VI 编辑器的文本过滤器，它以全屏幕的方式按页显示文本文件 的内容。more 指令中内置了若干快捷键，详见操作说明。

1. 基本语法 ：more 要查看的文件

2. 操作说明：

   | 操作说明       | 功能说明                                |
   | -------------- | --------------------------------------- |
   | 空白键 (space) | 代表向下翻一页                          |
   | Enter          | 代表向下翻『一行』                      |
   | q              | 代表立刻离开 more，不再显示该文件内容。 |
   | Ctrl+F         | 向下滚动一屏                            |
   | ctal+B         | 返回上一屏                              |
   | =              | 输出当前行的行号                        |
   | ：f            | 输出文件名和当前行的行号                |

3. 操作实例

   ```cmd
   [root@linux1 soft]# more a.text
   ```

### 7.2.12 less 分屏显示文件内容

less 指令用来分屏查看文件内容，它的功能与 more 指令类似，但是比 more 指令更加 强大，支持各种显示终端。less 指令在显示文件内容时，并不是一次将整个文件加载之后 才显示，而是根据显示需要加载内容，对于显示大型文件具有较高的效率

1. 基本语法： less 要查看的文件

2. 操作说明

   | 操作       | 功能说明                                         |
   | ---------- | ------------------------------------------------ |
   | 空白键     | 向下翻动一页                                     |
   | [pagedown] | 向下翻动一页                                     |
   | [pageup]   | 向上翻动一页；                                   |
   | /字串      | 向下搜寻『字串』的功能；n：向下查找；N：向上查找 |
   | ?字串      | 向上搜寻『字串』的功能，n：向上查找；N：向下查找 |
   | q          | 离开 less 这个程序；                             |

3. **经验技巧 ：**用SecureCRT时[pagedown]和[pageup]可能会出现无法识别的问题。

4. **实例操作**

   ```cmd
   [root@linux1 ~]# less anaconda-ks.cfg 
   ```

### 7.2.13 echo

echo 输出内容到控制台

1. **基本语法**：echo [选项] [输出内容]

2. 选项      -e： 支持反斜线控制的字符转换

   | 控制字符 | 作用      |
   | -------- | --------- |
   | \\\      | 输出\本身 |
   | \n       | 换行符    |
   | \t       | 制表符    |

3. 实例

   ```cmd
   [root@linux1 ~]# echo -e "hello\tworld"
   hello	world
   [root@linux1 ~]# echo hello world
   hello world
   ```

### 7.2.14 head 显示文件头部内容

head 用于显示文件的开头部分内容，默认情况下 head 指令显示文件的前 10 行

1. 语法： 	

   - head 文件 （功能描述：查看文件头10行内容）
   -  head -n 5 文件 （功能描述：查看文件头5行内容，5可以是任意行数）

2. 选项说明

   | 选项       | 功能                   |
   | ---------- | ---------------------- |
   | -n《行数》 | 指定显示头部内容的行数 |

3. 实操案例

   ```cmd
   [root@linux1 ~]# head -n 2 anaconda-ks.cfg 
   #version=DEVEL
   # System authorization information
   ```

### 7.2.15 tail 输出文件尾部内

tail 用于输出文件中尾部的内容，默认情况下 tail 指令显示文件的后 10 行内容。

1. 基本语法：

   - tail 文件 （功能描述：查看文件尾部10行内容）
   - tail -n 5 文件 （功能描述：查看文件尾部5行内容，5可以是任意行数） 
   - tail -f 文件 （功能描述：实时追踪该文档的所有更新

2. 选项说明

   | 选项     | 功能                                 |
   | -------- | ------------------------------------ |
   | -n<行数> | 输出文件尾部 n 行内容                |
   | -f       | 显示文件最新追加的内容，监视文件变化 |

3. 实操案例

   ```cmd
   [root@linux1 ~]# tail -n 2 anaconda-ks.cfg 
   pwpolicy luks --minlen=6 --minquality=1 --notstrict --nochanges --notempty
   %end
   ```

### 7.2.16 > 输出重定向和 >> 追加

1. 基本语法：

   - （1）ls -l > 文件 （功能描述：列表的内容写入文件 a.txt 中（覆盖写））
   -  （2）ls -al >> 文件 （功能描述：列表的内容追加到文件 aa.txt 的末尾） 
   - （3）cat 文件 1 > 文件 2 （功能描述：将文件 1 的内容覆盖到文件 2） 
   - （4）echo “内容”

2. 实操案例

   ```cmd
   [root@linux1 module]# ls -l> soft/a.text
   [root@linux1 module]# vim soft/a.text
   [root@linux1 module]# cd soft
   [root@linux1 soft]# ls -l>> a.text
   ```

   ```
   [root@linux1 soft]# echo hello -l>> a.text
   [root@linux1 soft]# vim a.text
   ```

   

### 7.2.17 ln 软链接

> 软链接也称为符号链接，类似于 windows 里的快捷方式，有自己的数据块，主要存放 了链接其他文件的路径。

1. 基本语法：ln -s [原文件或目录] [软链接名] （功能描述：给原文件创建一个软链接）

2. 经验技巧：删除软链接： rm -rf 软链接名，而不是 rm -rf 软链接名/ ，**如果使用 rm -rf 软链接名/ 删除**😎，会把软链接对应的真实目录下内容删掉 查询：通过 ll 就可以查看，列表属性第 1 位是 l，尾部会有位置指向。

3. 案例实操：添加软连接

   ```cmd
   [root@linux1 module]# ln -s soft/a.text mmtext
   [root@linux1 module]# ls
   mmtext  soft  software
   ```
   
   删除软连接
   
   ```cmd
   [root@linux1 module]# rm mmtext
   rm：是否删除符号链接 "mmtext"？y
   ```
   
   注意：弱愿文件或文件夹以及被删除，软连接失效




### 7.2.18 history 查看已经执行过历史命令

1. 基本语法：history （功能描述：查看已经执行过历史命令）

2. 案例实操：

   ```cmd
   [root@linux1 soft]# history
       1  cd/opt
       2  cs/opt/
       3  cd/opt/
       4  cd/opt
       5  cd:/opt
       6  opt
       7  cd/opt
   ```

## 7.3 时间日期类

1. 基本语法：date [OPTION]... [+FORMAT]

2. 选项说明

   |      选项      | 功能                                           |
   | :------------: | ---------------------------------------------- |
   | -d<时间字符串> | 显示指定的“时间字符串”表示的时间，而非当前时间 |
   |  -s<日期时间>  | 设置系统日期时间                               |

3. 参数说明

   | 参数            | 功能                         |
   | --------------- | ---------------------------- |
   | <+日期时间格式> | 指定显示时使用的日期时间格式 |

### 7.3.1 date 显示当前时间

1. 基本语法

   - （1）date （功能描述：显示当前时间） 
   - （2）date +%Y （功能描述：显示当前年份）
   -  （3）date +%m （功能描述：显示当前月份） 
   - （4）date +%d （功能描述：显示当前是哪一天）
   -  （5）date "+%Y-%m-%d %H:%M:%S" （功能描述：显示年月日时分秒）

2. 实操

   ```cmd
   [root@linux1 soft]# date +"%Y%m%d %H:&M%S"
   20230830 22:&M07
   ```

### 7.3.2 date 显示非当前时间

1. 基本语法：

   - （1）date -d '1 days ago' （功能描述：显示前一天时间）
   -  （2）date -d '-1 days ago' （功能描述：显示明天时间）

2. 案例：显示昨天

   ```
   [root@linux1 soft]# date -d "1 days ago"
   2023年 08月 29日 星期二 22:56:36 CST
   ```

   显示明天

   ```cmd
   [root@linux1 soft]# date -d "-1 days ago"
   2023年 08月 31日 星期四 22:57:45 CST
   ```

### 7.3.3 date 设置系统时间

1. 基本语法：**date -s 字符串时间**

2. 实操：（这里就不设置了😁）

   ```cmd
   [root@hadoop101 ~]# date -s "2017-06-19 20:52:18"
   ```

   插一段

**在Linux中，要设置系统的时区为北京时间，可以按照以下步骤进行操作：**

1. 打开终端窗口（Terminal）。

2. 输入以下命令以编辑时区设置文件：

   ```
   sudo vi /etc/timezone
   ```

   

3. 在编辑器中，将时区设置为"Asia/Shanghai"，然后保存并关闭文件。

4. 输入以下命令以重新设置系统时区：

   ```
   sudo dpkg-reconfigure --frontend noninteractive tzdata
   ```

   

5. 在出现的交互式界面中，选择"Asia"，然后在下一个界面中选择"Shanghai"，最后按照提示完成设置。

6. 最后，验证设置是否成功，可以使用以下命令查看系统时间：

   ```
   date
   ```

   

   如果显示的时间是北京时间，则表示设置成功。

请注意，以上步骤需要在具有管理员权限的用户下进行（或使用sudo）。

### 7.3.4 cal查看日历

1. 基本语法：cal [选项] （功能描述：不加选项，显示本月日历）

2. 选项说明

   | 选项       | 说明             |
   | ---------- | ---------------- |
   | 具体某一年 | 显示这一年的日历 |

3. 实操：

   ```cmd
   [root@linux1 soft]# cal
         八月 2023     
   日 一 二 三 四 五 六
          1  2  3  4  5
    6  7  8  9 10 11 12
   13 14 15 16 17 18 19
   20 21 22 23 24 25 26
   27 28 29 30 31
   
   [root@linux1 soft]# cal 2024
   
   ```

## 7.4 用户管理命令

### 7.4.1 useradd 添加新用户

1. 基本语法：useradd 用户名 （功能描述：添加新用户）

2. 案例实操：

   ```cmd
   [root@linux1 soft]# useradd ElySia
   [root@linux1 soft]# ls /home/
   ElySia  milan  tom  zwj
   ```

### 7.4.2 passwd 设置用户密码

1. 基本语法：passwd 用户名 （功能描述：设置用户密码）

2. 案例实操：

   ```cmd
   [root@linux1 soft]# passwd ElySia
   ```

### 7.4.3 id查看用户是否存在

1. 基本语法：id 用户名

2. 案例实操：

   ```
   [root@linux1 soft]# id ElySia
   uid=1005(ElySia) gid=1005(ElySia) 组=1005(ElySia)
   ```

### 7.4.4 cat /etc/passwd 查看创建了哪些用户

 1）案例实操 ：

```
[root@linux1 soft]#  cat /etc/passwd
```

### 7.4.5 su 切换用户

**su:switch user**

1. 基本语法：

   - su 用户名称 （功能描述：切换用户，只能获得用户的执行权限，**不能获得环境变量**）
   -  su - 用户名称 （功能描述：切换到用户并获得该用户的环境变量及执行权限）

2. 操作实例

   ```
   [root@linux1 soft]# su  ElySia
   [ElySia@linux1 soft]$ 
   ```

   ```
   [root@linux1 soft]# su - ElySia
   上一次登录：三 8月 30 23:13:55 CST 2023pts/0 上
   [ElySia@linux1 ~]$ 
   ```


### 7.4.6 userdel 删除用户

1.基本语法：

- 1）userdel 用户名 （功能描述：删除用户但保存用户主目录） 
- （2）userdel -r 用户名 （功能描述：用户和用户主目录，都删除）

2.选项说明

| 选项 | 说明                                             |
| ---- | ------------------------------------------------ |
| -r   | 删除用户的同时，删除与用户相关的所有文件。实操： |

3. 用户主目录未删除

```cmd
[root@linux1 module]# cd /home
[root@linux1 home]# ls
ElySia  milan  tom  zwj
[root@linux1 home]# userdel milan
[root@linux1 home]# ls
ElySia  milan  tom  zwj
```

### 7.4.7 who 查看登录用户信息

1. 语法：

   - （1）whoami （功能描述：显示自身用户名称） 
   - （2）who am i （功能描述：显示登录用户的用户名以及登陆时间）

2. 实操：

   - 显示当前自身用户名称

     ```cmd
     [root@linux1 home]# whoami
     root
     ```

   - 显示登录时用户的用户名

     ```cmd
     [root@linux1 home]# who am i
     root     pts/0        2023-08-31 16:19 (:0)
     ```

### 7.4.8 sudo 设置普通用户具有 root 权

1. 修改配置文件

   ```cmd
   vi /etc/sudoers
   ```

   修改 /etc/sudoers 文件，找到下面一行(91 行)，在 root 下面添加一行，如下所

   > \## Allow root to run any commands anywhere 
   >
   > root ALL=(ALL) ALL
   > 用户名 ALL=(ALL) ALL
   >
   > 或者配置成采用 sudo 命令时，不需要输入密码 

   > ## Allow root to run any commands anywhere
   >
   > root ALL=(ALL) ALL 
   >
   > 用户名 ALL=(ALL) NOPASSWD:ALL

> 要使Linux文件可读可写，你可以使用以下指令：
>
> 1. chmod命令：chmod命令用于更改文件的权限。要使文件可读可写，可以使用以下命令：
>
>    ```
>    chmod +rw 文件名
>    ```
>
>    
>
>    这将为文件添加读取和写入权限。
>
> 2. chown命令：chown命令用于更改文件的所有者。如果你是文件的所有者，你可以使用以下命令将文件的权限设置为可读可写：
>
>    ```
>    chown 用户名 文件名
>    ```
>
>    
>
>    将"用户名"替换为你的用户名，"文件名"替换为你要更改权限的文件名。
>
> 请注意，更改文件权限可能需要管理员权限或适当的权限。确保你有足够的权限来执行这些操作。

### 7.4.9 usermod 修改用户

1. 基本语法：usermod -g 用户组 用户名

2. 选项说明：

   | 选项 | 说明                                                   |
   | ---- | ------------------------------------------------------ |
   | -g   | 修改用户的初始登录组，给定的组必须存在。默认组 id 是 1 |

3. 案例实操

   ```cmd
   [root@linux1 home]# groupadd nuwushen
   [root@linux1 home]# usermod -g nuwushen ElySia
   [root@linux1 home]# id ElySia
   uid=1005(ElySia) gid=1006(nuwushen) 组=1006(nuwushen)
   ```

   

## 7.5 用户组管理命令

> 每个用户都有一个用户组，系统可以对一个用户组中的所有用户进行集中管理。不同 Linux 系统对用户组的规定有所不同， 如Linux下的用户属于与它同名的用户组，这个用户组在创建用户时同时创建。 用户组的管理涉及用户组的添加、删除和修改。组的增加、删除和修改实际上就是对 /etc/group文件的更新。

### 7.5.1 groupadd 新增组

### 7.5.2 groupdel 删除组

### 7.5.3 groupmod 修改组

1）基本语法 groupmod -n 新组名 老组名

### 7.5.4 cat /etc/group 查看创建了哪些组

案例

```cmd
[root@linux1 home]# cat /etc/group 
root:x:0:
bin:x:1:
daemon:x:2:
sys:x:3:
adm:x:4:
tty:x:5:
```

## 7.6 文件权限类

### 7.6.1 文件属性

> Linux系统是一种典型的多用户系统，不同的用户处于不同的地位，拥有不同的权限。
> 为了保护系统的安全性，Linux系统对不同的用户访问同一文件（包括目录文件）的权限做
> 了不同的规定。在Linux中我们可以使用ll或者ls -l命令来显示一个文件的属性以及文件所属
> 的用户和组。

1. 从左到右的 10 个字符表示![image-20230831171738447](C:\Users\张吉勇\AppData\Roaming\Typora\typora-user-images\image-20230831171738447.png)如果没有权限，就会出现减号[ - ]而已。从左至右用0-9这些数字来表示:

   -    (1)0 首位表示类型 在Linux中第一个字符代表这个文件是目录、文件或链接文件等等 - 代表文件 d 代表目录 l 链接文档(link file)；
   - （2）第1-3位确定属主（该文件的所有者）拥有该文件的权限。---User 
   - （3）第4-6位确定属组（所有者的同组用户）拥有该文件的权限，---Group 
   - （4）第7-9位确定其他用户拥有该文件的权限 ---Other

2. rwx 作用文件和目录的不同解释 

   - 作用到文件： 
     - [ r ]代表可读(read): 可以读取，查看
     -  [ w ]代表可写(write): 可以修改，但是不代表可以删除该文件，删除一个文件的前 提条件是对该文件所在的目录有写权限，才能删除该文件行
   - 作用到目录：
     -  [ r ]代表可读(read): 可以读取，ls查看目录内容 
     - [ w ]代表可写(write): 可以修改，目录内创建+删除+重命名目录
     -  [ x ]代表可执行(execute):可以进入该目录

3. 实操

   ```cmd
   [root@linux1 ~]# ll
   总用量 1236
   -rw-------. 1 root root    1991 8月  14 16:14 anaconda-ks.cfg
   -rw-r--r--. 1 root root    2039 8月  14 16:19 initial-setup-ks.cfg
   drwxr-xr-x. 9 1001 1001    4096 8月  27 23:14 nginx-1.25.2
   -rw-r--r--. 1 root root 1214903 8月  27 22:32 nginx-1.25.2.tar.gz
   drwxr-xr-x. 2 root root    4096 8月  18 21:36 prod
   drwxr-xr-x. 2 root root    4096 8月  14 16:19 公共
   drwxr-xr-x. 2 root root    4096 8月  14 16:19 模板
   drwxr-xr-x. 2 root root    4096 8月  14 16:19 视频
   drwxr-xr-x. 2 root root    4096 8月  14 16:19 图片
   drwxr-xr-x. 2 root root    4096 8月  14 16:19 文档
   drwxr-xr-x. 2 root root    4096 8月  14 16:19 下载
   drwxr-xr-x. 2 root root    4096 8月  14 16:19 音乐
   drwxr-xr-x. 2 root root    4096 8月  14 16:19 桌面
   ```

### 7.6.2 chmod 改变权限

1. 基本语法![image-20230831200126020](C:\Users\张吉勇\AppData\Roaming\Typora\typora-user-images\image-20230831200126020.png)

   - 第一种方式变更权限 chmod [{ugoa}{+-=}{rwx}] 文件或目录 
   - 第二种方式变更权限 chmod [mode=421 ] [文件或目录]

2. 经验技巧: **u:所有者 g:所有组 o:其他人 a:所有人(u、g、o 的总和)**,**r=4 w=2 x=1 rwx=4+2+1=7**'

3. 实操案例：

   - 1）修改文件使其所属主用户具有执行权限

     ```
     [root@hadoop101 ~]# cp xiyou/dssz/houge.txt ./
     [root@hadoop101 ~]# chmod u+x houge.txt
     ```

   - （2）修改文件使其所属组用户具有执行权限

     ```
     [root@hadoop101 ~]# chmod g+x houge.txt
     ```

   - （3）修改文件所属主用户执行权限,并使其他用户具有执行权限

     ```
     [root@hadoop101 ~]# chmod u-x,o+x houge.txt
     ```

   - （4）采用数字的方式，设置文件所有者、所属组、其他用户都具有可读可写可执行权
     限。

     ```
     [root@hadoop101 ~]# chmod 777 houge.txt
     ```

   - （5）修改整个文件夹里面的所有文件的所有者、所属组、其他用户都具有可读可写可
     执行权限。

     [root@hadoop101 ~]# chmod -R 777 xiyou/****

### 7.6.3 chown 改变所有者

1. 基本语法：chown [选项] [最终用户] [文件或目录] （功能描述：改变文件或者目录的所有者）

2. 选项说明

   | 选项 | 说明     |
   | ---- | -------- |
   | -R   | 递归操作 |

3. 案例实操：

   - 修改文件所有者

     ```cmd
     [root@linux1 module]# chown ElySia a.text
     [root@linux1 module]# ll
     总用量 12
     -rw-r--r--. 1 ElySia root  185 8月  31 20:07 a.text
     drwxr-xr-x. 2 root   root 4096 8月  31 16:22 soft
     drwxr-xr-x. 2 root   root 4096 8月  30 15:26 software
     ```

   - 递归改变文件夹所有者和所有组

     ```cmd
     [root@hadoop101 xiyou]# ll
     drwxrwxrwx. 2 root root 4096 9 月 3 21:20 xiyou
     [root@hadoop101 xiyou]# chown -R atguigu:atguigu xiyou/
     [root@hadoop101 xiyou]# ll
     drwxrwxrwx. 2 atguigu atguigu 4096 9 月 3 21:20 xiyou
     ```

### 7.6.4 chgrp 改变所属组

1. 基本语法：chgrp [最终用户组] [文件或目录] （功能描述：改变文件或者目录的所属组）

2. 实操：

   - 修改文件的所属组

     ```shell
     [root@hadoop101 ~]# chgrp root houge.txt
     [root@hadoop101 ~]# ls -al
     -rwxrwxrwx. 1 atguigu root 551 5 月 23 13:02 houge.txt
     ```

## 7.7 搜索查找类

### 7.7.1 find 查找文件或者目录

> find 指令将从指定目录向下递归地遍历其各个子目录，将满足条件的文件显示在终端

1. 基本语法：find [搜索范围] [选项

2. 选项说明

   | 选项            | 功能                                                         |
   | --------------- | ------------------------------------------------------------ |
   | -name<查询方式> | 按照指定的文件名查找模式查找文件                             |
   | -user<用户名    | 查找属于指定用户名所有文件                                   |
   | -size<文件大小> | 按照指定的文件大小查找文件,单位为:<br/>b —— 块（512 字节）<br/>c —— 字节<br/>w —— 字（2 字节）<br/>k —— 千字节<br/>M —— 兆字节<br/>G —— 吉字 |

3. 操作实例：

   - 按名字：

     ```shell
     [root@linux1 module]# find / -name a.text
     /opt/module/soft/a.text
     ```

   - 按用户名

     ```shell
     [root@linux1 module]# find /opt -user root
     ```

   - 在/home目录下查找大于1m的文件（+n 大于 -n小于 n等于

     ```shell
     [root@linux1 module]# find /home -size +1024
     /home/tom/.cache/tracker/meta.db-wal
     /home/tom/.cache/tracker/meta.db
     ```


### 7.7.2 locate 快速定位文件路径

> locate 指令利用事先建立的系统中所有文件名称及路径的 locate 数据库实现快速定位给 定的文件。Locate 指令无需遍历整个文件系统，查询速度较快。为了保证查询结果的准确 度，管理员必须定期更新 locate 时

1.实操：

```shell
[root@linux1 ~]# locate a.text
/opt/module/soft/a.text
```



### 7.7.3 grep 过滤查找及“|”管道符

> 管道符，“|”，表示将前一个命令的处理结果输出传递给后面的命令处理

1. 基本语法：grep 选项 查找内容 源文

2. | 选项 | 功能               |
   | ---- | ------------------ |
   | -n   | 显示匹配行及行号。 |

3. 实操：查找某文件在第几行

   ```shell
   [root@linux1 ~]# ls | grep -n ngi
   3:nginx-1.25.2
   4:nginx-1.25.2.tar.gz
   ```

## 7.8 压缩和解压类

### 7.8.1 gzip/gunzip 压缩

1. 语法：

   - 基本语法 gzip 文件 （功能描述：压缩文件，只能将文件压缩为*.gz 文件） （**源文件不保留**😎）
   - gunzip 文件.gz （功能描述：解压缩文件命令）

2. 经验

   - 只能压缩文件不能压缩目录
   - 不保留原来的文件
   - 同时多个文件会产生多个压缩包

3. 实操：

   - 压缩文件

     ```shell
     [root@linux1 soft]# gzip a.text
     [root@linux1 soft]# ls
     a.text.gz  mytext
     ```

   - 解压文件

     ```shell
     [root@linux1 soft]# gunzip a.text.gz 
     [root@linux1 soft]# ls
     a.text  mytext
     ```

### 7.8.2 zip/unzip 压缩文件

1. 基本语法：

   - zip [选项] XXX.zip 将要压缩的内容 （功能描述：压缩文件和目录的命令）
   - unzip [选项] XXX.zip （功能描述：解压缩文件）

2. 选项功能

   | 选项（zip） | 功能     |
   | ----------- | -------- |
   | -r          | 压缩目录 |

   | 选项（unzip） | 功能                     |
   | ------------- | ------------------------ |
   | -d<目录>      | 指定解压后文件的存放目录 |

3. 经验： zip 压缩命令在windows/linux都通用，可以压缩目录且保留源文件。

### 7.8.3 tar 打包

1. 基本语法：**tar [选项] XXX.tar.gz  将要打包进去的内容 （功能描述：打包目录，压缩后的 文件格式.tar.gz）**

2. 选项说明：

   | 选项 | 说明               |
   | ---- | ------------------ |
   | -c   | 产生.tar 打包文件  |
   | -v   | 显示详细信息       |
   | -f   | 指定压缩后的文件名 |
   | -z   | 打包同时压缩       |
   | -x   | 解包.tar 文件      |
   | -C   | 解压到指定目录     |

   

## 7.9 磁盘查看和分区类

### 7.9.1 du 查看文件和目录占用的磁盘空间

> du: disk usage 磁盘占用情

1. 基本语法：du 目录/文件 （功能描述：显示目录下每个子目录的磁盘使用情况）

2. 选项说明：

   | 选项                       | 功能                                                   |
   | -------------------------- | ------------------------------------------------------ |
   | -h                         | 以人们较易阅读的 GBytes, MBytes, KBytes 等格式自行显示 |
   | -a                         | 不仅查看子目录大小，还要包括文件                       |
   | -c                         | 显示所有的文件和子目录大小后，显示总和                 |
   | -s                         | 只显示总和                                             |
   | --max-depth=n--max-depth=n | 指定统计子目录的深度为第 n 层                          |

3. 案例

   ```shell
   [root@linux1 soft]# du -sh
   8.0K	.
   您在 /var/spool/mail/root 中有新邮件
   ```
   

### 7.9.2 df 查看磁盘空间使用情况

df: disk free 空余磁盘

1. 基本语法：df 选项 （功能描述：列出文件系统的整体磁盘使用量，检查文件系统的磁盘空间占 用情况）

2. 选项功能

   | 选项 | 功能                                                   |
   | ---- | ------------------------------------------------------ |
   | -h   | 以人们较易阅读的 GBytes, MBytes, KBytes 等格式自行显示 |

3. 案例实操：

   ```shell
   [root@linux1 soft]# df -h
   文件系统        容量  已用  可用 已用% 挂载点
   devtmpfs        974M     0  974M    0% /dev
   tmpfs           991M     0  991M    0% /dev/shm
   tmpfs           991M   24M  968M    3% /run
   tmpfs           991M     0  991M    0% /sys/fs/cgroup
   /dev/sda3        17G   12G  4.4G   73% /
   /dev/sda1       976M  142M  768M   16% /boot
   overlay          17G   12G  4.4G   73% /var/lib/docker/overlay2/0542f57541d825cb843545cfeb94c5db2b350a8cc3e9af45fdfd82fd5ccff2a1/merged
   overlay          17G   12G  4.4G   73% /var/lib/docker/overlay2/e0e0bf227aadd2dd76350a1829f880809b439b197eed46e02c4b190c6c7d10d0/merged
   overlay          17G   12G  4.4G   73% /var/lib/docker/overlay2/a84287a195668f8af4921957bcfa749a3d3c08af3c58dc58a87165ce4eb0a2c2/merged
   overlay          17G   12G  4.4G   73% /var/lib/docker/overlay2/c681a694c81f1e3cc93dd9a2c2c46c240808b6514ee6394951f8b3c7f0798875/merged
   overlay          17G   12G  4.4G   73% /var/lib/docker/overlay2/ca0e2d2fbb6990cd62608e98a61dd2afbe142ea1abbec1a6f3b36cb692a689c9/merged
   tmpfs           199M   40K  198M    1% /run/user/0
   /dev/sr0        4.4G  4.4G     0  100% /run/media/root/CentOS 7 x86_64
   ```

### 7.9.3 lsblk 查看设备挂载情况

1）基本语法
lsblk （功能描述：查看设备挂载情况）
2）选项说明

| 选项 | 功能                                     |
| ---- | ---------------------------------------- |
| -f   | 查看详细的设备挂载情况，显示文件系统信息 |

### 7.9.4 mount/umount 挂载/卸载

> 对于Linux用户来讲，不论有几个分区，分别分给哪一个目录使用，它总归就是一个根
> 目录、一个独立且唯一的文件结构。
> Linux中每个分区都是用来组成整个文件系统的一部分，它在用一种叫做“挂载”的处理
> 方法，它整个文件系统中包含了一整套的文件和目录，并将一个分区和一个目录联系起来，
> 要载入的那个分区将使它的存储空间在这个目录下获得

1. 挂载前准备（必须要有光盘或者已经连接镜像文件）![image-20230901181044676](C:\Users\张吉勇\AppData\Roaming\Typora\typora-user-images\image-20230901181044676.png)![image-20230901181125048](C:\Users\张吉勇\AppData\Roaming\Typora\typora-user-images\image-20230901181125048.png)

2. 基本语法：

   - mount [-t vfstype] [-o options] device dir （功能描述：挂载设备）
   -  umount 设备文件名或挂载点 （功能描述：卸载设备）

3. 参数说明

   | 参数       | 说明                                                         |
   | ---------- | ------------------------------------------------------------ |
   | -t vfstype | 指定文件系统的类型，通常不必指定。mount 会自动选择正确的类<br/>型。常用类型有：<br/>光盘或光盘镜像：iso9660<br/>DOS fat16 文件系统：msdos<br/>Windows 9x fat32 文件系统：vfat<br/>Windows NT ntfs 文件系统：ntfs<br/>Mount Windows 文件网络共享：smbfs<br/>UNIX(LINUX) 文件网络共享：nfs |
   | -o options | 主要用来描述设备或档案的挂接方式。常用的参数有：<br/>loop：用来把一个文件当成硬盘分区挂接上系统<br/>ro：采用只读方式挂接设备<br/>rw：采用读写方式挂接设备<br/>iocharset：指定访问文件系统所用字符集 |
   | device     | 要挂接(mount)的设备                                          |
   | dir        | 设备在系统上的挂接点(mount point)                            |

   

