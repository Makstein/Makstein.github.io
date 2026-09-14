---
title: Unity Editor 摄像机获取透明 PNG 图片
date: "2026-09-03 17:53 +0800"
categories: 
  - Game Development
  - Unity
tags:
  - unity
---

- **安装工具**：打开 `Window` -> `Package Manager`，在 Packages 中选择 Unity Registry，找到并安装 **Recorder**。

- **打开面板**：点击 `Window` -> `General` -> `Recorder` -> `Recorder Window`。

- **添加记录器**：
    - 点击 **Add Recorder**，选择 **Image Sequence**（序列帧图片）。 [[1](https://developer.unity.cn/projects/5e2d8d83edbc2a473b8458a9)]

- **核心参数设置**：
    - **Source**：选择 **Targeted Camera**（指定摄像机），并将你的目标摄像机拖入。
    - **Output File**：设置保存路径和文件名。
    - **Image Format**：选择 **PNG**。
    - **Capture Alpha**：**必须勾选**此项以保留透明通道。 [[1](https://developer.unity.cn/projects/5e2d8d83edbc2a473b8458a9)]

- **摄像机自身设置**：
    - 将该摄像机的 `Clear Flags` 设置为 **Solid Color**。
    - 将 `Background` 颜色的 Alpha（透明度）通道拉到 **0**。 [[1](https://blog.csdn.net/qq_26900671/article/details/103651522)]

- **开始录制**：运行游戏（Play），点击 Recorder 面板中的 **Start Recording** 即可生成透明 PNG。 [[1](https://zhuanlan.zhihu.com/p/573966479)]