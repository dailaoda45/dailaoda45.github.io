---
title: 记录PyInstaller打包常用命令参数
author: 戴昌益
date: 2024--07-15
updated：2024--07-15
tags: [学习]
categories: 文|技
---

## 记录PyInstaller打包常用命令参数

总是忘记命令，每次使用都需要去百度查。在这里我记录一下常用的一些参数命令。

### 基本打包命令

结论

```
pyinstaller --onefile --windowed --icon=myicon.ico --name MyApp your_script.py
```



1. **安装 PyInstaller**

   如果你还没有安装 `PyInstaller`，可以通过以下命令进行安装：

   ```
   bash
   pip install pyinstaller
   ```
   
2. **基本打包命令**

   使用以下命令可以将 `your_script.py` 打包成一个独立的可执行文件：

   ```
   bash
   pyinstaller your_script.py
   ```

### 常用选项

1. **--onefile**

   将所有内容打包成一个单独的可执行文件：

   ```
   bash
   pyinstaller --onefile your_script.py
   ```
   
2. **--windowed**

   不会显示控制台窗口（适用于 GUI 应用程序）：

   ```
   bash
   pyinstaller --onefile --windowed your_script.py
   ```
   
3. **--name**

   指定生成的可执行文件的名称：

   ```
   bash
   pyinstaller --onefile --windowed --name MyApp your_script.py
   ```
   
4. **--icon**

   指定应用程序图标：

   ```
   bash
   pyinstaller --onefile --windowed --icon=myicon.ico your_script.py
   ```
   
5. **--add-data**

   添加数据文件和其他资源文件：

   ```
   bash
   pyinstaller --onefile --add-data 'datafile.dat;.' your_script.py
   ```
   
   在 Windows 上，文件路径和目标路径用分号 `;` 分隔，在 Unix 系统上用冒号 `:` 分隔。
   
6. **--hidden-import**

   指定隐藏导入（在某些情况下 PyInstaller 可能无法自动检测到所有导入的模块）：

   ```
   bash
   pyinstaller --onefile --hidden-import module_name your_script.py
   ```

### 示例

综合使用上述选项，可以使用以下命令打包一个名为 `your_script.py` 的 Python 脚本，生成一个名为 `MyApp.exe` 的独立可执行文件，图标为 `myicon.ico`，并包含额外的数据文件 `datafile.dat`：

```
bash
pyinstaller --onefile --windowed --name MyApp --icon=myicon.ico --add-data 'datafile.dat;.' your_script.py
```

### 打包输出文件

执行上述命令后，PyInstaller 会在当前目录生成 `dist` 和 `build` 目录：

- `dist` 目录：包含打包后的可执行文件。
- `build` 目录：包含临时文件和构建文件。

### 处理特定需求

如果你的项目有特定需求，比如打包多个脚本、包含特定的第三方库等，可以根据需要调整 `PyInstaller` 命令和参数。详细的参数和选项可以参考 [PyInstaller 官方文档](https://pyinstaller.readthedocs.io/en/stable/usage.html)。

希望这些信息能帮助你顺利打包你的 Python 项目。