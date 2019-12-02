# Mission 1

### ubuntu 一个让你吃饭的系统

##### 命令行大全

```
1.查看目录结构命令

ls(list)功能：列出目录内容

格式：ls[参数][文件或目录]

-a或--all    所有文件和目录。注意隐藏文件、特殊目录、以“.”开头的和以“..”开头的

-l    使用详细格式列表

-t    用文件和目录的更改时间排序

-r   反向排序

--help   在线帮助

常用：

ls   -l             列出当前目录下的文件信息（此命令很常用，简化的格式为 ll）

ls   -al           列出当前目录下的文件信息（包括隐藏文件，特殊目录）

ll    /home/     显示根目录下home目录下的内容
2.切换目录命令

cd(change directory)功能：切换目录

语法：cd[目录]

常用：

cd   ~       当前用户主目录

cd   /        根目录

cd   -        上一次访问的目录

cd   ..       上一级目录

cd            当前用户主目录

 

touch   1.txt    在当前目录创建一个文件1.txt

clear：清除屏幕

 
3.创建目录命令

pwd:显示当前工作目录

mkdir: 创建目录

mkdir   a :当前目录下创建文件夹a

mkdir  /root/b  :在根目录下的root下创建目录b

mkdir  -pv  /root/c/e/d :在根目录下的root下创建目录结构c/e/d（一下创建多级目录）

-p：父目录不存在情况下先生成父目录

-v：显示命令执行过程中的详细信息

[注]：如果是文件开头是-，如果是文件夹开头是d且文件夹名为黑体(如下图所示)

 
4.文件浏览

[注]：按tab键可以自动补齐文件名

cat   文件名：显示指定文件的所有内容（用于文件内容少的情况）

more  文件名：分页显示文件内容，还支持直接跳转行等功能（用于文件内容多的情况）

Enter ：向下n行，需要定义。默认为1行

空格键：向下滚动一屏  或 Ctrl+F

B    返回上一屏  或Ctrl+B

q   退出more

less [参数]  文件名 ：分页显示文件内容，操作更详细

参数：-m 显示类似more命令的百分比        -N   显示每行的行号     两个参数可以结合用  -mN

空格键：前进一页 或 page down

b：后退一页   或 page up

d：前进半页

u：后退半页

Enter：前进一行 或 方向键向下

y：后退一行  或 方向键向上

/字符串：向下搜索

？字符串：向上搜索

v：进入vim编辑器

tall命令：用来显示指定文件末尾内容，不指定文件时，作为输入信息进行处理。常用查看日志文件。

tail[必要参数][选择参数][文件]

 -n<行数> 显示行数

-f 循环读取
5.文件操作

1.复制命令：cp

cp(copy)功能：复制文件或目录

语法：cp[参数]   [源文件或目录]    [目标文件或目录]

-r或--recursive   递归处理，将指定目录下的文件与子目录一并处理

 -b  覆盖文件时，可以将源文件做一个备份

例如：

复制文件：

cp   1.txt   2.txt

cp -b  1.txt  2.txt  ：如果覆盖文件时,可以将源文件做一个备份

cp  ./1.txt   ../   ：将当前目录下的1.txt复制到父级目录

cp  /root/1.txt   /bin/2.txt   ：将/root下的1.txt文件复制到根目录下的bin目录下的2.txt中

复制目录：(无论是单层目录还是多层目录都可以复制):

cp  -r  ./a  ./b

cp  -r  /root/a  /root/z

2.移动命令：mv

mv（move）功能：移动或更名现有的文件或目录

语法：mv [源文件或目录][目标文件或目录]

-f  或 --force   若目标文件或目录与现有的文件目录重复，则直接覆盖现有的文件或目录

剪切文件：mv    ./1.txt    /root    将当前目录下的1.txt文件 剪切到root目录下

重命名文件：mv  ./1.txt   ./2.txt      将当前目录下的1.txt文件重命名为2.txt

3.删除命令：rm

rm功能：删除文件或目录

语法：rm [-dfirv][--help][--version][文件或目录...]

-f 或 --force   强制删除文件或目录

-r 或 -R 或 --recursive   递归处理，将指定目录下的所有文件及子目录一并处理

强制删除文件：rm   -f   ./1.txt      

强制删除目录：rm   -rf   ./a      

 

4.查找命令：find

find功能：查找文件或目录

语法：find[目录...][参数]

-name  指定字符串作为寻找文件或目录的范本样式

例如：find  /root/  -name  'test*'   查找root目录下的文件开头是test的文件和文件夹，*是通配符 。注意字符串要用单引号引起来。
6.文档编辑

vi或vim命令

基本操作

1.vim  文件名   ：进入一般模式（不能输入）

2.按下 i 从一般模式，进入到插入模式

3.按下esc从插入模式，退出到一般模式

4.在一般模式下，输入:wq,退出编辑。

7.管道

linux提供管道符号 “|”  作用是“命令1”的输出内容，将作为“命令2”的输入内容。一般与grep命令一起使用

格式：命令1 | 命令2

1.grep命令

功能：用于过滤/搜索特定字符。可使用正则表达式 能多种命令配合使用。

格式：grep [option] pattern [file]       grep   参数  过滤条件   文件        （-i 或 --ignore-case        忽略字符大小写的差别）

例如：grep   -i   one  /root/1.txt      显示root目录下的1.txt文件中含有one字符的一行数据（忽略大小写）   

格式：其他命令 | grep  参数  过滤条件

例如：cat   /root/1.txt  |  grep  -i  one     在cat命令输出结果基础上，进行过滤

 
8.系统命令

1.ps命令

任务管理器：ps  -ef        查看当前所有进程（包括执行ps命令的那个时刻进程信息）

格式：ps [参数]

-e  此参数的效果和指定“A”参数相同，显示所有程序

-f  显示UID,PPIP,C与STIME栏位

例如：ps -ef  |  grep -i mysql     过滤出mysql这个进程

2.kill命令

kill功能：删除执行中的程序或工作

语法：kill[参数][程序]

-l<信息编号>       若不加<信息编号>选项，则-l参数会列出全部的信息名称。

kill  -9  ：表示强制终止

格式：kill    -9    pid

可先通过ps -ef 查找出所要删除的进程pid，再通过kill -9 pid 终止进程

3.ifconfig命令

功能：显示网络设备

格式：ping  主机名或ip地址    （按ctrl+c停止ping）
9.备份压缩：tar命令

tar功能：文件备份压缩

格式：tar      参数       压缩后的文件名      被压缩的文件名

           tar      参数       被解压的文件名      -C  指定目录            （如果省略 -C 指定目录，则解压到当前文件夹）

-c 建立一个压缩文件的参数指令（create）--压缩

-x 解开一个压缩文件的参数指令（extract）--解压

-z 是否需要用gzip压缩

-v 压缩的过程中显示文件（verbose）

-f 使用档名，在f之后要立即接档名（file）

常用解压参数组合：zxvf

常用压缩参数组合：zcvf

例如：

  tar  -zcvf  /root/1.tar   /root/a     将root目录下的a文件夹压缩成1.tar,放在root目录下。

  tar  -zxvf  ./1.tar        将当前目录下的1.tar文件解压缩

[注]：如果后缀名为.tar.gz的压缩包用-zxvf   如果后缀名为.tar的压缩包用-xvf
10.关机  重启

Linux centos 重启命令：reboot

Linux centos 关机命令：halt

 
11.文件权限：chmod命令

chmod功能：变更文件或目录的权限

语法：chmod [参数][<权限范围><符号><权限代号>]

-R  或 --recursive   递归处理，将指定目录下的所有文件及子目录一并处理

--权限范围的表示法如下：

u：User  即文件或目录的拥有者

g：Group 即文件或目录的所属群组

o：Other  除了文件或目录拥有者或所属群组之外，其他用户皆属于这个范围

a：All        即全部的用户，包含拥有者，所属群组及其他用户。

--符号

+ 添加权限

- 取消权限

-- 有关权限代号的部分

r：读取权限，数字代号为“4”

w：写入权限，数字代号为“2”

x：执行或切换权限，数字代号为“1”

- ：不具任何权限，数字代号为“0”

777 ：所有权限

[注]：3=1+2（wx）   5=4+1(rx)

 

mkdir xxx  创建xxx目录

例如：

chmod    u-rwx   xxx    取消xxx目录的用户“读写执行”权限

chmod    g-rwx   xxx    取消xxx目录的组“读写执行”权限

chmod    777      xxx    给xxx目录添加所有权限       

 
```

```
 Ubuntu常用命令大全

查看软件xxx安装内容
#dpkg -L xxx

查找软件
#apt-cache search 正则表达式
查找文件属于哪个包
#dpkg -S filename apt-file search filename

查询软件xxx依赖哪些包
#apt-cache depends xxx

查询软件xxx被哪些包依赖
#apt-cache rdepends xxx

增加一个光盘源
#sudo apt-cdrom add

系统升级
#sudo apt-get update
#sudo apt-get upgrade
#sudo apt-get dist-upgrade

清除所以删除包的残余配置文件
#dpkg -l |grep ^rc|awk ‘{print $2}’ |tr [”"n”] [” “]|sudo xargs dpkg -P -

编译时缺少h文件的自动处理
#sudo auto-apt run ./configure

查看安装软件时下载包的临时存放目录
#ls /var/cache/apt/archives

备份当前系统安装的所有包的列表
#dpkg –get-selections | grep -v deinstall > ~/somefile

从上面备份的安装包的列表文件恢复所有包
#dpkg –set-selections < ~/somefile sudo dselect

清理旧版本的软件缓存
#sudo apt-get autoclean

清理所有软件缓存
#sudo apt-get clean

删除系统不再使用的孤立软件
#sudo apt-get autoremove

查看包在服务器上面的地址
#apt-get -qq –print-uris install ssh | cut -d"’ -f2
系统



查看内核
#uname -a

查看Ubuntu版本
#cat /etc/issue

查看内核加载的模块
#lsmod

查看PCI设备
#lspci

查看USB设备
#lsusb

查看网卡状态
#sudo ethtool eth0

查看CPU信息
#cat /proc/cpuinfo

显示当前硬件信息
#lshw
硬盘

查看硬盘的分区
#sudo fdisk -l

查看IDE硬盘信息
#sudo hdparm -i /dev/hda

查看STAT硬盘信息
#sudo hdparm -I /dev/sda
或 
#sudo apt-get install blktool
#sudo blktool /dev/sda id

查看硬盘剩余空间
#df -h
#df -H

查看目录占用空间
#du -hs 目录名

优盘没法卸载
#sync fuser -km /media/usbdisk
内存

查看当前的内存使用情况
#free -m
进程
查看当前有哪些进程
#ps -A

中止一个进程
#kill 进程号(就是ps -A中的第一列的数字) 或者 killall 进程名

强制中止一个进程(在上面进程中止不成功的时候使用)
#kill -9 进程号 或者 killall -9 进程名

图形方式中止一个程序
#xkill 出现骷髅标志的鼠标，点击需要中止的程序即可

查看当前进程的实时状况
#top

查看进程打开的文件
#lsof -p

ADSL 配置 ADSL
#sudo pppoeconf

ADSL手工拨号
#sudo pon dsl-provider

激活 ADSL
#sudo /etc/ppp/pppoe_on_boot

断开 ADSL
#sudo poff

查看拨号日志
#sudo plog

如何设置动态域名
#首先去http://www.3322.org申请一个动态域名
#然后修改 /etc/ppp/ip-up 增加拨号时更新域名指令 sudo vim /etc/ppp/ip-up
#在最后增加如下行 w3m -no-cookie -dump
网络

根据IP查网卡地址
#arping IP地址

查看当前IP地址
#ifconfig eth0 |awk ‘/inet/ {split($2,x,”:”);print x[2]}’

查看当前外网的IP地址
#w3m -no-cookie -dumpwww.edu.cn|grep-o‘[0-9]"{1,3"}".[0-9]"{1,3"}".[0-9]"{1,3"}".[0-9]"{1,3"}’
#w3m -no-cookie -dumpwww.xju.edu.cn|grep-o’[0-9]"{1,3"}".[0-9]"{1,3"}".[0-9]"{1,3"}".[0-9]"{1,3"}’ 
#w3m -no-cookie -dump ip.loveroot.com|grep -o’[0-9]"{1,3"}".[0-9]"{1,3"}".[0-9]"{1,3"}".[0-9]"{1,3"}’

查看当前监听80端口的程序
#lsof -i :80

查看当前网卡的物理地址
#arp -a | awk ‘{print $4}’ ifconfig eth0 | head -1 | awk ‘{print $5}’

立即让网络支持nat
#sudo echo 1 > /proc/sys/net/ipv4/ip_forward
#sudo iptables -t nat -I POSTROUTING -j MASQUERADE

查看路由信息
#netstat -rn sudo route -n

手工增加删除一条路由
#sudo route add -net 192.168.0.0 netmask 255.255.255.0 gw 172.16.0.1
#sudo route del -net 192.168.0.0 netmask 255.255.255.0 gw 172.16.0.1

修改网卡MAC地址的方法
#sudo ifconfig eth0 down 关闭网卡
#sudo ifconfig eth0 hw ether 00:AA:BB:CC:DD:EE 然后改地址
#sudo ifconfig eth0 up 然后启动网卡

统计当前IP连接的个数
#netstat -na|grep ESTABLISHED|awk ‘{print $5}’|awk -F: ‘{print $1}’|sort|uniq -c|sort -r -n
#netstat -na|grep SYN|awk ‘{print $5}’|awk -F: ‘{print $1}’|sort|uniq -c|sort -r -n

统计当前20000个IP包中大于100个IP包的IP地址
#tcpdump -tnn -c 20000 -i eth0 | awk -F “.” ‘{print $1″.”$2″.”$3″.”$4}’ | sort | uniq -c | sort -nr | awk ‘ $1 > 100 ‘

屏蔽IPV6
#echo “blacklist ipv6″ | sudo tee /etc/modprobe.d/blacklist-ipv6
服务

添加一个服务
#sudo update-rc.d 服务名 defaults 99

删除一个服务
#sudo update-rc.d 服务名 remove

临时重启一个服务
#/etc/init.d/服务名 restart

临时关闭一个服务
#/etc/init.d/服务名 stop

临时启动一个服务
#/etc/init.d/服务名 start
设置

配置默认Java使用哪个
#sudo update-alternatives –config java

修改用户资料
#sudo chfn userid

给apt设置代理
#export http_proxy=http://xx.xx.xx.xx:xxx

修改系统登录信息
#sudo vim /etc/motd
中文

转换文件名由GBK为UTF8
#sudo apt-get install convmv convmv -r -f cp936 -t utf8 –notest –nosmart *

批量转换src目录下的所有文件内容由GBK到UTF8
#find src -type d -exec mkdir -p utf8/{} "; find src -type f -exec iconv -f GBK -t UTF-8 {} -o utf8/{} "; mv utf8/* src rm -fr utf8

转换文件内容由GBK到UTF8
#iconv -f gbk -t utf8 $i > newfile

转换 mp3 标签编码
#sudo apt-get install python-mutagen find . -iname “*.mp3” -execdir mid3iconv -e GBK {} ";

控制台下显示中文
#sudo apt-get install zhcon 使用时，输入zhcon即可
文件

快速查找某个文件
#whereis filename
#find 目录 -name 文件名

查看文件类型
#file filename

显示xxx文件倒数6行的内容
#tail -n 6 xxx

让tail不停地读地最新的内容
#tail -n 10 -f /var/log/apache2/access.log

查看文件中间的第五行（含）到第10行（含）的内容
#sed -n ‘5,10p’ /var/log/apache2/access.log

查找包含xxx字符串的文件
#grep -l -r xxx .

全盘搜索文件(桌面可视化)
gnome-search-tool

查找关于xxx的命令
#apropos xxx man -k xxx

通过ssh传输文件
#scp -rp /path/filenameusername@remoteIP:/path
#将本地文件拷贝到服务器上
#scp -rpusername@remoteIP:/path/filename/path
#将远程文件从服务器下载到本地

查看某个文件被哪些应用程序读写
#lsof 文件名

把所有文件的后辍由rm改为rmvb
#rename ’s/.rm$/.rmvb/’ *

把所有文件名中的大写改为小写
#rename ‘tr/A-Z/a-z/’ *

删除特殊文件名的文件，如文件名：–help.txt
#rm — –help.txt 或者 rm ./–help.txt

查看当前目录的子目录
#ls -d */. 或 echo */.

将当前目录下最近30天访问过的文件移动到上级back目录
#find . -type f -atime -30 -exec mv {} ../back ";

将当前目录下最近2小时到8小时之内的文件显示出来
#find . -mmin +120 -mmin -480 -exec more {} ";

删除修改时间在30天之前的所有文件
#find . -type f -mtime +30 -mtime -3600 -exec rm {} ";

查找guest用户的以avi或者rm结尾的文件并删除掉
#find . -name ‘*.avi’ -o -name ‘*.rm’ -user ‘guest’ -exec rm {} ";

查找的不以java和xml结尾,并7天没有使用的文件删除掉
#find . ! -name *.java ! -name ‘*.xml’ -atime +7 -exec rm {} ";

统计当前文件个数
#ls /usr/bin|wc -w

统计当前目录个数
#ls -l /usr/bin|grep ^d|wc -l

显示当前目录下2006-01-01的文件名
#ls -l |grep 2006-01-01 |awk ‘{print $8}’
FTP

上传下载文件工具-filezilla
#sudo apt-get install filezilla

filezilla无法列出中文目录？
站点->字符集->自定义->输入：GBK

本地中文界面
1）下载filezilla中文包到本地目录，如~/
2）#unrar x Filezilla3_zhCN.rar
3) 如果你没有unrar的话，请先安装rar和unrar
#sudo apt-get install rar unrar
#sudo ln -f /usr/bin/rar /usr/bin/unrar
4）先备份原来的语言包,再安装；实际就是拷贝一个语言包。
#sudo cp /usr/share/locale/zh_CN/filezilla.mo /usr/share/locale/zh_CN/filezilla.mo.bak
#sudo cp ~/locale/zh_CN/filezilla.mo /usr/share/locale/zh_CN/filezilla.mo
5）重启filezilla,即可！
解压缩

解压缩 xxx.tar.gz
#tar -zxvf xxx.tar.gz

解压缩 xxx.tar.bz2
#tar -jxvf xxx.tar.bz2

压缩aaa bbb目录为xxx.tar.gz
#tar -zcvf xxx.tar.gz aaa bbb

压缩aaa bbb目录为xxx.tar.bz2
#tar -jcvf xxx.tar.bz2 aaa bbb

解压缩 RAR 文件
1) 先安装
#sudo apt-get install rar unrar
#sudo ln -f /usr/bin/rar /usr/bin/unrar
2) 解压
#unrar x aaaa.rar

解压缩 ZIP 文件
1) 先安装
#sudo apt-get install zip unzip
#sudo ln -f /usr/bin/zip /usr/bin/unzip
2) 解压
#unzip x aaaa.zip
Nautilus

显示隐藏文件
Ctrl+h

显示地址栏
Ctrl+l

特殊 URI 地址
* computer:/// - 全部挂载的设备和网络
* network:/// - 浏览可用的网络
* burn:/// - 一个刻录 CDs/DVDs 的数据虚拟目录
* smb:/// - 可用的 windows/samba 网络资源
* x-nautilus-desktop:/// - 桌面项目和图标
*file:///- 本地文件
* trash:/// - 本地回收站目录
* ftp:// - FTP 文件夹
* ssh:// - SSH 文件夹
* fonts:/// - 字体文件夹，可将字体文件拖到此处以完成安装
* themes:/// - 系统主题文件夹

查看已安装字体
在nautilus的地址栏里输入”fonts:///“，就可以查看本机所有的fonts
程序

详细显示程序的运行信息
#strace -f -F -o outfile

日期和时间

设置日期
#date -s mm/dd/yy

设置时间
#date -s HH:MM

将时间写入CMOS
#hwclock –systohc

读取CMOS时间
#hwclock –hctosys

从服务器上同步时间
#sudo ntpdate time.nist.gov
#sudo ntpdate time.windows.com

控制台

不同控制台间切换
Ctrl + ALT + ← Ctrl + ALT + →

指定控制台切换
Ctrl + ALT + Fn(n:1~7)

控制台下滚屏
SHIFT + pageUp/pageDown

控制台抓图
#setterm -dump n(n:1~7)
数据库

mysql的数据库存放在地方
#/var/lib/mysql

从mysql中导出和导入数据
#mysqldump 数据库名 > 文件名 #导出数据库
#mysqladmin create 数据库名 #建立数据库
#mysql 数据库名 < 文件名 #导入数据库

忘了mysql的root口令怎么办
#sudo /etc/init.d/mysql stop
#sudo mysqld_safe –skip-grant-tables 
#sudo mysqladmin -u user password ‘newpassword”
#sudo mysqladmin flush-privileges

修改mysql的root口令
#sudo mysqladmin -uroot -p password ‘你的新密码’
其它

下载网站文档
#wget -r -p -np -khttp://www.21cn.com
· r：在本机建立服务器端目录结构；
· -p: 下载显示HTML文件的所有图片；
· -np：只下载目标站点指定目录及其子目录的内容；
· -k: 转换非相对链接为相对链接。

如何删除Totem电影播放机的播放历史记录
#rm ~/.recently-used

如何更换gnome程序的快捷键
点击菜单，鼠标停留在某条菜单上，键盘输入任意你所需要的键，可以是组合键，会立即生效； 如果要清除该快捷键，请使用backspace

vim 如何显示彩色字符
#sudo cp /usr/share/vim/vimcurrent/vimrc_example.vim /usr/share/vim/vimrc

如何在命令行删除在会话设置的启动程序
#cd ~/.config/autostart rm 需要删除启动程序

如何提高wine的反应速度
#sudo sed -ie ‘/GBK/,/^}/d’ /usr/share/X11/locale/zh_CN.UTF-8/XLC_LOCALE

#chgrp
[语法]: chgrp [-R] 文件组 文件…
[说明]： 文件的GID表示文件的文件组，文件组可用数字表示， 也可用一个有效的组名表示，此命令改变一个文件的GID，可参看chown。
-R 递归地改变所有子目录下所有文件的存取模式
[例子]:
＃chgrp group file 将文件 file 的文件组改为 group

#chmod
[语法]: chmod [-R] 模式 文件…
或 chmod [ugoa] {+|-|=} [rwxst] 文件…
[说明]: 改变文件的存取模式，存取模式可表示为数字或符号串，例如：
＃chmod nnnn file ， n为0-7的数字，意义如下:
4000 运行时可改变UID
2000 运行时可改变GID
1000 置粘着位
0400 文件主可读
0200 文件主可写
0100 文件主可执行
0040 同组用户可读
0020 同组用户可写
0010 同组用户可执行
0004 其他用户可读
0002 其他用户可写
0001 其他用户可执行
nnnn 就是上列数字相加得到的，例如 chmod 0777 file 是指将文件 file 存取权限置为所有用户可读可写可执行。
-R 递归地改变所有子目录下所有文件的存取模式
u 文件主
g 同组用户
o 其他用户
a 所有用户
+ 增加后列权限
- 取消后列权限
= 置成后列权限
r 可读
w 可写
x 可执行
s 运行时可置UID
t 运行时可置GID
[例子]:
＃chmod 0666 file1 file2 将文件 file1 及 file2 置为所有用户可读可写
＃chmod u+x file 对文件 file 增加文件主可执行权限
＃chmod o-rwx 对文件file 取消其他用户的所有权限

#chown
[语法]: chown [-R] 文件主 文件…
[说明]: 文件的UID表示文件的文件主，文件主可用数字表示， 也可用一个有效的用户名表示，此命令改变一个文件的UID，仅当此文件的文件主或超级用户可使用。
-R 递归地改变所有子目录下所有文件的存取模式
[例子]:
#chown mary file 将文件 file 的文件主改为 mary
#chown 150 file 将文件 file 的UID改为150
Ubuntu命令行下修改网络配置

以eth0为例
1. 以DHCP方式配置网卡
编辑文件/etc/network/interfaces:
#sudo vi /etc/network/interfaces
并用下面的行来替换有关eth0的行:
# The primary network interface - use DHCP to find our address
auto eth0
iface eth0 inet dhcp
用下面的命令使网络设置生效:
#sudo /etc/init.d/networking restart
当然,也可以在命令行下直接输入下面的命令来获取地址
#sudo dhclient eth0

2. 为网卡配置静态IP地址
编辑文件/etc/network/interfaces:
#sudo vi /etc/network/interfaces
并用下面的行来替换有关eth0的行:
# The primary network interface
auto eth0
iface eth0 inet static
address 192.168.3.90
gateway 192.168.3.1
netmask 255.255.255.0
network 192.168.3.0
broadcast 192.168.3.255
将上面的ip地址等信息换成你自己就可以了.

用下面的命令使网络设置生效:
#sudo /etc/init.d/networking restart

3. 设定第二个IP地址(虚拟IP地址)
编辑文件/etc/network/interfaces:
#sudo vi /etc/network/interfaces
在该文件中添加如下的行:
auto eth0:1
iface eth0:1 inet static
address 192.168.1.60
netmask 255.255.255.0
network x.x.x.x
broadcast x.x.x.x
gateway x.x.x.x
根据你的情况填上所有诸如address,netmask,network,broadcast和gateways等信息.
用下面的命令使网络设置生效:
#sudo /etc/init.d/networking restart

4. 设置主机名称(hostname)
使用下面的命令来查看当前主机的主机名称:
#sudo /bin/hostname
使用下面的命令来设置当前主机的主机名称:
#sudo /bin/hostname newname
系统启动时,它会从/etc/hostname来读取主机的名称.

5. 配置DNS
首先,你可以在/etc/hosts中加入一些主机名称和这些主机名称对应的IP地址,这是简单使用本机的静态查询.
要访问DNS 服务器来进行查询,需要设置/etc/resolv.conf文件.
假设DNS服务器的IP地址是192.168.3.2, 那么/etc/resolv.conf文件的内容应为:
search test.com
nameserver 192.168.3.2
安装AMP服务

如果采用Ubuntu Server CD开始安装时，可以选择安装，这系统会自动装上apache2,php5和mysql5。下面主要说明一下如果不是安装的Ubuntu server时的安装方法。
用命令在Ubuntu下架设Lamp其实很简单，用一条命令就完成。在终端输入以下命令：
#sudo apt-get install apache2 mysql-server php5 php5-mysql php5-gd #phpmyadmin
装好后，mysql管理员是root，无密码，通过http://localhost/phpmyadmin就可以访问mysql了

修改 MySql 密码
终端下输入：
#mysql -u root
#mysql> GRANT ALL PRIVILEGES ON *.* TO root@localhost IDENTIFIED BY “123456″;
’123456‘是root的密码，可以自由设置，但最好是设个安全点的。
#mysql> quit; 退出mysql

apache2的操作命令
启动：#sudo /etc/init.d/apache2 start
重启：#sudo /etc/init.d/apache2 restart
关闭：#sudo /etc/init.d/apache2 stop
apache2的默认主目录：/var/www
```

```
简单命令十二：APT高级软件包管理工具

①  sudo apt-get update        ##更新所有软件包

②  apt-get常用命令

命令
	

描述

apt-get  install
	

下载并安装软件包

apt-get  upgrade
	

下载并安装本系统上已有的软件包的最新版

apt-get  remove
	

卸载特定的软件包

apt-get source
	

下载特定软件的源代码

apt-get clean
	

删除所有的已下载的包文件

```

```
简单命令六：权限设置

r(读)，w(写)，x(执行)三种权限

①   ls  -l /home/login   ##带有-l的ls指令可以查看文件的完整属性，包括权限等。

②   ls  -lb  /home    ##查看目录完整属性，用-lb选项

③   ls  -l          ##不带文件名作为参数，表示列出当前目录下的所有文件

④   sudo   chown libaobao  days    ##改变文件所有权

⑤   sudo   chown -R  libaobao  /home  ##参数-R可以改变/home目录下所有文件目录的权限

⑥   sudo  chgrp workgroup days   ##将文件days的属性组设置为workgroup组

⑦   sudo  chgrp root /home    ##将一个路径下的所有文件和目录的属性组设置为root ,它和chown指令差不多，也可以使用-R选项（功能相同）

⑧   chmod u+x days     ##改变文件权限命令，文件属主（u）,文件属组（g）,其他人（o）和所有人（a）,而权限包含读（r）,写（w）,执行（x）,这条命令就是增加了属主对文件的执行权限。

⑨   chmod  a-x days  ##表示删除所有人对days文件的执行权限。

⑩   chmod  ug = rw ,o =r    days  ##这条命令表示同时赋予属主和属组对days文件的读写权限，其他人读权限

⑪  chmod u=g       days ##此命令旨在说明把属主和属组的权限设为相同，只有文件的属主和root用户才有权限对文件进行修改操作。

```



##### 常见问题

 

```
背景

我有一个Ubuntu VM，我经常用它来测试很多应用程序，并写了很多关于它们的文章。在不久前，我偶然发现了一个名为“Ubunsys”的有用系统配置应用程序。在测试时，我在尝试显示隐藏的启动项时搞坏了.bashrc文件。每次打开终端时，都会显示如下错误消息：

-bash: /home/sk/.bashrc: line 68: syntax error near unexpected token `)'

-bash: /home/sk/.bashrc: line 68: `xterm*|rxvt*)'

Ubuntu VM实际上是出于测试目的，因此我可以轻松删除它并在几分钟内创建一个新的。但是，我不想这样做。在搜索合适的解决方案时，我在Ubuntu社区中遇到了一个可靠的答案，它描述了如何将.bashrc恢复为默认设置。我照着它的方法操作，并在几分钟内解决了问题。以下就为你分享该方法

 

将.bashrc文件还原到Ubuntu中的默认设置方法

在Ubuntu系统的/etc/skel/目录中有.bashrc文件的默认版本。因此，如果你遇到.bashrc文件问题，可以轻松将其恢复为默认设置，按照下面的方法操作。

首先，使用以下命令备份当前的.bashrc文件：

$ cp ~/.bashrc ~/.bashrc.bak

然后，将.bashrc文件的默认版本复制到你当前的版本，如下所示：

$ cp /etc/skel/.bashrc ~/

最后，运行以下命令以更新更改：

$ source ~/.bashrc

 

结语

如果你在不知情的情况下在.bash_profile或.bashrc文件中添加了一些代码，并且这些代码已经给系统带来不稳定的因素，请按照上述步骤将它们恢复为默认值。我在Ubuntu 16.04 LTS中对此进行了测试，并且能够正常运行。该方法可以适用其它的Ubuntu版本及衍生版本。
```

