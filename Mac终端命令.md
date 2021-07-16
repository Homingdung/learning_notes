# 基本介绍

command+q 退出 终端

# 目录和文件

+ 显示当前命令行：pwd

+ 查看目录下内容：ls
  + 更多参数：ls -l
  + 查看隐藏文件 ls -la

+ 进入一个指定目录：cd
  + cd Desktop/
  + cd ../: 上一层目录
  + c d ./:当前目录
+ 新建一个目录：mkdir
+ 重命名或移动文件/目录: mv
  + mv image/image2 
+ 复制文件和目录:cp
  + cp 2.png 3.png
  + cp -R 文件夹名 文件名2 （一般文件夹操作都要用 -R）

+ 删除：rm
  + rm -fR new_folder

+ 查看文件目录大小：du -sh
+ 查看命令帮助信息：man





+ 创建文件：touch
  + touch test.docx
+ 打开文件: open
+ 打开编辑文本文件：vim
  + :q 退出
+ 查找文件:find
  + find ./ -name "*.png", 目录路径要以/结尾
  + Find /etc/ -name "*.txt"

+ 查看文件类型：file
+ **删除所有文件(谨慎)**：rm -fR (R 递归删除，一层一层删除)
+ 进入主目录： cd ~



# 快捷键：

+ control +C：中断命令的执行
+ control+A: 返回行首
+ control+E：返回行尾

# 常用网络命令

+ ping: ping www.baidu.com
+ ifconfig: 查看/配置网络接口
  + ifconfig en0
+ networksetup -listallhardwareports
+ ipconfig

# 获取电脑运行温度，风扇转速

``` shell
sudo powermetrics
```



# 定时关机 重启 睡眠

```shell
shutdown
shutdown [-h|-s|-r] time [提示信息]

# 十分钟后睡眠
sudo shutdwon -s +10
```



# vim 编辑器

命令模式：把输入的内容当作命令看待

+ vim xx.txt

输入模式：输入的内容当文本内容看待

+ i a o r
+ esc退回命令模式

底线命令模式：输入的内容当成命令看待，在底部显示

+ 冒号：

+ 保存：w
+ 退出：q
+ ：wq





# Git

[https://blog.csdn.net/hcbbt/article/details/11651229]

github 创建项目仓库后

复制 SSH地址

```git
cd /Users/peter/Desktop/
git clone SSH地址
```

提交修改首先切换到文件夹路径

```git
cd /Users/peter/Desktop/2deg_billiard_matlab
//文件添加到仓库 (.代表所有文件)
git add .
//把文件提交到仓库
git commit -m "first commit"
//上传到 github
git push
```





