---
title: UE5 什么时候使用 Live Coding
date: 2025-02-07 16:41 +0800
categories:
  - Game Development
  - Unreal Engine
tags:
  - ue
---
根据 Reddit 上的评论，**不应该** 在以下情况使用 Live Coding
- 更改了 .h 头文件
- 更改了 .cpp 中的构造函数
- 更改了 UPROPERTY 或 UFUNCTION 中的属性
- 更改了 GameInstance 或 GameInstance 子系统中的逻辑