---
title: UE UnrealBuildTool failed with exit code 0xe0434352
date: 2026-05-30 11:10 +0800
categories:
  - Game Development
  - Unreal Engine
tags:
  - bug
---
问题：正常从 Rider 编译启动 UE 时出现 `UE UnrealBuildTool failed with exit code 0xe0434352` 问题，原因多半是更改了工程的根目录结构，例如新建文件夹，新建文件等。

## 方法一（网上看到的，没用）
解决：win+R，输入%localappdata%后确定，删除UnrealBuildTools，返回工程重新编译。

## 方法二
看了下 git 最近更改的文件，在项目 .uproject 中，发现 Plugin 中有个模块：
```json
{  
    "Name": "ModelingToolsEditorMode",  
    "Enabled": true,  
    "TargetAllowList": [  
       "Editor"  
    ]  
},
```
其中的 `TargetAllowList` 部分消失了，同时，最后多出了几行：
```json
"TargetPlatforms": [],
"AdditionalRootDirectories": [],
"AdditionalPluginDirectories": [],
"EpicSampleNameHash": ""
```
将 TargetAllowList 重新添加，并删除最后一行的 EpicSampleNameHash 后就可以成功编译了

修改：不对，可能是 git 状态出了问题，编译时检查完 git status 就直接退出了，提交所有修改后才能正常编译