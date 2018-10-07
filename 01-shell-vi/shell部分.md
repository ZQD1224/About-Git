## 1.1    什么是shell

在计算机科学中，Shell俗称壳，用来区别于Kernel（核），是指“提供使用者使用界面”的软件（命令解析器）。它类似于[DOS](http://baike.baidu.com/view/365.htm)下的command和后来的cmd.exe。它接收用户命令，然后调用相应的应用程序。?                                                  

## 1.2    shell分类

1、图形界面shell：通过提供友好的可视化界面，调用相应应用程序，如windows系列操作系统，Linux系统上的图形化应用程序GNOME、KDE等。

2、命令行shell：通过键盘输入特定命令的方式，调用相应的应用程序，如windows系统的cmd.exe、Windows PowerShell，Linux系统的Bourne shell ( sh)、Bourne Again shell ( bash)等。

## 1.3    认识bash这个shell

在window系统下使用bash，需要一个软件，这个软件模拟集成了bash大部分命令。

各个 shell 的功能都差不多， Linux 默认使用 bash ，所以我们主要学习bash的使用。

1，`bash`命令格式

命令 [-options][参数]，如：tar  zxvf  demo.tar.gz

查看帮助：命令 --help

2、bash常见命令

pwd (Print Working Directory) 查看当前目录

cd (Change Directory) 切换目录，如 cd /etc

ls (List) 查看当前目录下内容，如 ls -al

mkdir (Make Directory) 创建目录，如 mkdir blog

touch 创建文件，如 touch index.html

cat 查看文件全部内容，如 cat index.html

more/less 查看文件，如more /etc/passwd、less /etc/passwd

rm (remove) 删除文件，如 rm index.html、rm -rf  blog

rmdir (Remove Directory) 删除文件夹，只能删除空文件夹，不常用

mv (move) 移动文件或重命名，如 mv index.html ./demo/index.html

cp (copy) 复制文件，cp index.html ./demo/index.html

head 查看文件前几行，如 head -5 index.html

tail 查看文件后几行 –n –f，如 tail index.html、tail -f -n 5 index.html 

tab 自动补全，连按两次会将所有匹配内容显示出来

history 查看操作历史

\> 和 >>重定向，如echo hello world! > README.md，>覆盖 >>追加

wget 下载，如wget https://nodejs.org/dist/v4.4.0/node-v4.4.0.tar.gz

tar 解压缩，如tar zxvf node-v4.4.0.tar.gz

curl 网络请求，如curl http://www.baidu.com

whoami 查看当前用户

| 管道符可以将多个命令连接使用，上一次（命令）的执行结果当成下一次（命令）的参数。

grep 匹配内容，一般结合管道符使用