# Auto-Editor GUI 批量处理工具使用说明

## 功能介绍

Auto-Editor GUI是一个图形界面工具，可以方便地使用auto-editor批量处理视频文件，提供以下功能：

1. 支持通过拖放方式添加视频文件
2. 可以批量处理多个不同目录下的视频
3. 自定义输出文件命名（添加后缀）
4. 可调整处理参数（margin、audio threshold等）
5. 实时显示处理进度和日志

## 安装要求

使用本工具需要满足以下条件：

1. 已安装auto-editor命令行工具 (`pip install auto-editor`)
2. Python 3.6或更高版本
3. 安装tkinter和tkinterdnd2拖放支持库

```bash
pip install tkinterdnd2
```

## 使用方法

### 启动程序

```bash
python auto_editor_gui.py
```

### 添加视频文件

有三种方式添加视频文件：

1. **拖放添加**：直接将视频文件或包含视频的文件夹拖入程序界面
2. **浏览添加**：点击"添加文件"按钮选择一个或多个视频文件
3. **添加文件夹**：点击"添加文件夹"按钮选择一个包含视频的文件夹

### 调整处理参数

在"处理参数设置"部分，可以调整以下参数：

- **边距 (margin)**：设置剪辑前后保留的时间（单位：秒）
- **音频阈值 (threshold)**：设置检测静音的阈值（0-1之间）
- **有声部分速度**：有声部分的播放速度
- **静音部分速度**：静音部分的播放速度
- **输出文件后缀**：输出文件名添加的后缀（默认为"_edited"）

### 开始处理

1. 添加所有需要处理的视频文件后，点击"开始处理"按钮
2. 程序会按顺序处理每个视频文件
3. 处理过程中可以在日志区域查看实时进度
4. 如需停止处理，点击"停止处理"按钮

### 处理结果

- 所有处理完成的视频文件会保存在原视频所在的目录中
- 输出文件名格式为：原文件名 + 自定义后缀 + 原扩展名
- 可以在文件列表中查看每个文件的处理状态（等待处理/处理中/完成/失败）

## 常见问题

1. **如果拖放功能不可用**：
   - 确保已安装tkinterdnd2库
   - 某些系统可能需要额外配置

2. **处理失败的原因**：
   - auto-editor不支持该视频格式
   - 视频文件可能已损坏
   - 视频文件可能被其他程序占用

3. **如何处理非常大的视频文件**：
   - 处理大文件可能需要较长时间，请耐心等待
   - 可以考虑先将视频分割成较小的片段再处理

## 注意事项

- 处理视频需要足够的磁盘空间
- 输出文件会保存在与原视频相同的目录中
- 如果已存在同名输出文件，将会被覆盖