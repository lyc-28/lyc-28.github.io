---
title: vscode的下载与c/c++环境配置
date: 2025-12-19 12:52:34
tags: C/C++
categories: C/C++
---
# <center>🎨 VS Code 下载 & C/C++ 环境配置</center>
## <center><font face="楷体" size=8>J.W</font></center>
## 1️⃣ 安装包一键直达
|软件|版本|下载链接|备注|
|:---|:---|:---|:---|
|VS Code|最新稳定版|[📥官方直链](https://code.visualstudio.com/download)|建议勾选 “添加到 PATH”|
MinGW-w64 |8.1.0 (posix-seh)	|[📥 SourceForge](https://sourceforge.net/projects/mingw-w64/files/Toolchains%20targetting%20Win64/Personal%20Builds/mingw-builds/8.1.0/threads-posix/seh/)|解压即用，无需安装|
 - ⚠️ 注意：MinGW 解压路径不要含中文或空格，推荐 D:\mingw64
## 2️⃣ 安装 VS Code 插件
- 打开 VS Code → 左侧图标栏 Extensions（或快捷键 Ctrl+Shift+X）
- 搜索并安装
  - 🌏 Chinese (Simplified) – 中文语言包
- 重启 VS Code，界面变成中文即成功。
## 3️⃣ 配置环境变量
步骤	图解操作
 - ① 复制路径	进入解压后的 D:\mingw64\bin，复制地址栏路径
 - ② 打开系统设置	Win + S 搜索 “编辑系统环境变量” → 环境变量
 - ③ 编辑 Path	在 系统变量 里双击 Path → 新建 → 粘贴路径 → 一路 确定
 - ④ 验证	打开 新 的 PowerShell/CMD，输入：gcc --version 出现版本号即 OK
 - ✅ 成功示意
gcc (x86_64-posix-seh-rev0, Built by MinGW-W64 project) 8.1.0
## 4️⃣ 创建你的第一个 C 项目
- 新建文件夹 D:\VSCode-C\Hello
- VS Code → 文件 → 打开文件夹 → 选中 Hello
- 信任作者 → 勾选 “信任”
- 新建文件 hello.c 并贴入：
```
#include <stdio.h>

int main(void) {
    printf("Hello, 世界!\n");
    return 0;
}
```
## 5️⃣ 配置 IntelliSense & 编译任务
- 目的操作路径
- 指定编译器	Ctrl+Shift+P → C/C++: 编辑配置(UI) 
- 编译器路径：选择 D:\mingw64\bin\gcc.exe
- IntelliSense 模式：windows-gcc-x64
- 生成构建任务	Ctrl+Shift+P → 任务：配置任务 
- 选择 C/C++: gcc.exe 生成活动文件
- 完成后，左侧会自动生成 .vscode 文件夹，内含：
- .vscode
├── tasks.json   // 构建脚本
├── c_cpp_properties.json // IntelliSense 配置
## 6️⃣ 编译 & 运行
|场景|快捷键|说明|
|:---|:---|:---|
|VS Code 内置终端|	F5	|自动编译+运行，可打断点调试|
|外部终端	|Ctrl+F5 or F8	|弹出独立 CMD 窗口|

🎉 第一次运行效果
```
Hello, 世界!
请按任意键继续 . . .
```
## 7️⃣ 美化彩蛋：一键主题推荐
在 Extensions 里搜索安装，瞬间颜值拉满：
- 主题 / 图标包	安装关键词
  - 🌕 Moonlight	moonlight theme
  + 🌈 SynthWave '84	synthwave
  + 📁 Material Icon Theme	material icon
## 8️⃣ 常见问题速查表
|现象|	解决|
|:---|:---|
|gcc 不是内部或外部命令|	环境变量未生效，重启终端/系统|
|undefined reference to 'WinMain'	|文件后缀写成 .c 而非 .cpp；或 main 拼写错误|
|中文输出乱码	|终端输入 chcp 65001 切换 UTF-8，或代码里使用 system("chcp 65001");|
## 🎊 恭喜！ 至此，你已拥有高颜值、可调试、支持中文的 C/C++ 开发环境。