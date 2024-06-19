---
title: UE5 动画蓝图 Layered Blend Per Bone 节点
date: 2024-06-19 15:03 +0800
categories:
  - Game Development
  - Unreal Engine
tags:
  - ue
  - animation
---
![Node](/assets/img/202406/LayeredBlendPerBoneNode.png)
_Layered Blend Per Bone Node_

以角色边开枪边走路为例

- Base Pose: 基础动作，当前例子下为 `角色走路动作`
- Blend Poses0: 需要混合到基础动作上的动作，当前例子下为 `角色开枪动作`

![Property](/assets/img/202406/LayeredBlendPerBoneProperty.png)
_Layered Blend Per Bone Property_

- 骨骼名称：在分支过滤器模式下，选择需要混合到基础动作上的动画所需的骨骼，本例中为 `角色开枪动作所需的角色上半身骨骼` 根据骨骼树输入 `spine_01`
- 混合深度：0和1都是从第一根骨骼开始混合，本例中为 `spine_01`，设置值大于1时从设置骨骼的向下设置值根骨骼开始100%混合，之前的骨骼为阶段递增混合