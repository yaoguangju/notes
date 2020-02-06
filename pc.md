| 问题                           | 地址                                                         |
| ------------------------------ | ------------------------------------------------------------ |
| 搜狗输入法如何设置符号的快捷键 | [1](https://zhidao.baidu.com/question/1644022246817904460.html) |
| win10 激活180天的方法          | [1](https://jingyan.baidu.com/article/77b8dc7fa35ed96174eab608.html) |
|                                |                                                              |
|                                |                                                              |
|                                |                                                              |
|                                |                                                              |
|                                |                                                              |
|                                |                                                              |
|                                |                                                              |

##### 右键计算机磁盘管理打不开

```
创建1.reg文件，写入以下代码，运行
Windows Registry Editor Version 5.00  
[HKEY_CLASSES_ROOT\CLSID\{20D04FE0-3AEA-1069-A2D8-08002B30309D}\shell\Manage\command]  
@=hex(2):25,00,77,00,69,00,6e,00,64,00,69,00,72,00,25,00,5c,00,73,00,79,00,73,\  
00,74,00,65,00,6d,00,33,00,32,00,5c,00,6d,00,6d,00,63,00,2e,00,65,00,78,00,\  
65,00,20,00,2f,00,73,00,20,00,25,00,77,00,69,00,6e,00,64,00,69,00,72,00,25,\  
00,5c,00,73,00,79,00,73,00,74,00,65,00,6d,00,33,00,32,00,5c,00,63,00,6f,00,\  
6d,00,70,00,6d,00,67,00,6d,00,74,00,2e,00,6d,00,73,00,63,00,00,00 
```

##### 解决WIN7不能把把软件图标放到任务栏的方法

```
把以下命令分别输入到开始-运行中（快速启动运行：Windows+R）
1. cmd /k reg add "HKEY_CLASSES_ROOT\lnkfile" /v IsShortcut /f
2. cmd /k reg add "HKEY_CLASSES_ROOT\piffile" /v IsShortcut /f
3. cmd /k taskkill /f /im explorer.exe & explorer.exe
现在你把桌面的图标或其他路径的程序直接拖到windows7的任务栏就可以了
```

##### 搭建ss

```
安装
wget --no-check-certificate https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks-libev.sh
chmod +x shadowsocks-libev.sh
./shadowsocks-libev.sh 2>&1 | tee shadowsocks-libev.log
卸载
./shadowsocks-libev.sh uninstall
```

##### github相关

```
把文件夹变成Git可管理的仓库
git init

暂存区的相关操作
git add 文件名      将文件添加到暂存区
git add .          将全部文件添加到暂存区
git status         查看暂存区的内容

上传文件到本地仓库
git commit -m'描述内容'

本地仓库和github仓库的关联
git remote add origin 新建库的地址
关联后 git pull origin master

上传本地仓库内容到github仓库
git push -u origin master

git的克隆操作
git clone 地址

git中文显示8进制字符串的解决办法
git config --global core.quotepath false
```

