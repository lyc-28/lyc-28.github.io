---
title: vscode的下载与c/c++环境配置
date: 2025-12-19 12:52:34
tags: C/C++
categories: C/C++
---
# <center><font face="宋体" size=10 font color=red> vscode的下载与c/c++环境配置</font></center>
## <center><font face="楷体" size=8>J.W</font></center>
### *一.下载*
1. 安装vscode
   - [vscode下载](https://code.visualstudio.com/download "vscode的下载")
2. 安装mingw64
   - [mingw64](https://sourceforge.net/projects/mingw-w64/files/Toolchains%20targetting%20Win64/Personal%20Builds/mingw-builds/8.1.0/threads-posix/seh/)
### *二.配置环境*
1. 安装vscode中的插件
- 点入extension安装中文插件Chinese (Simplified) (简体中文) Language Pac
- 重启vscode
- 然后安装插件C/C++
2. 配置环境变量
- 找到mingw64文件
- 按顺序点mingw64-bin 然后复制文件路径:就是文件地址
- 点击开始菜单
- 搜索编辑系统环境变量
- 打开，点击环境变量
- 下方系统变量
- 点击path再点编辑
 - 新建，然后粘贴刚刚复制的路径
- 然后一路确定
3. 配置C/C++编译环境
- 新建一个文件夹
- 打开vscode的资源管理器
- 点击打开文件夹
- 找到刚刚的文件夹，点击选择文件夹
- 勾选信任，然后选择是
- 然后点击左侧上方的新建文件
- 输入文件名加后缀，这里我们新建一个C语言文件后缀为.c
- 写一个简单的代码，例如:
  ```
  #include<stdio.h>
  int main()
  {
    printf("Hello,World!");
    return 0;
  }
  ```
- 按下ctrl+s保存代码
- 然后按下ctrl+shift+p打开搜索
- 搜索C/C++:编辑配置（ui）点入
- 找到编译器路径，点击它右边小三角
- 选择mingw64/bin/gcc.exe
- 下滑，找到intellisense
- 选择windows-gcc-x64模式
- 回到代码
- 点击上方终端，点击配置任务
- 选择C/C++:gcc.exe生成活动文件
- 然后左侧资源管理器会自动生成.vscode文件夹
- 说明成功了，然后就可以开始运行代码了
- 然后回到代码，再次点击终端，点击运行生成任务
- 再次选择C/C++:gcc.exe生成活动文件
- 然后再点终端，点击新建终端就行了
- 快捷键F5在vscode的终端运行代码F8在电脑上的终端运行代码
