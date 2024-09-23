---
title: UE5 BlueprintNativeEvents
date: 2024-09-14 15:52 +0800
categories:
  - Game Development
  - Unreal Engine
tags:
  - ue
  - ufunction
---
**BlueprintNativeEvents** 是 **UFUNCTION** 的一个函数说明符，作用是指定一个函数，使其可以在C++中实现，并且同时可以在蓝图中被重载

与 **BlueprintImplementableEvents** 不同，它不仅可以有蓝图实现，而且可以拥有一个C++实现

## 具体使用

```cpp
///Header (.h) function definition: 
//Override in BP to extend the base C++ functionality!
UFUNCTION(BlueprintNativeEvent, BlueprintCallable, Category="JoyBall")
float GetArmorRating() const;

/////////////////

///Source (.cpp) function Implementation:
float AJoyBall::GetArmorRating_Implementation() const
{
    //remember to call super / parent function in BP!
    V_LOG("C++ Happens First");
    return 100;
}
```

在蓝图重载函数中，可以调用父函数来使用C++的实现，并在此基础上进行扩展，或者不调用父函数，完全重写此函数

## 参考

[Tutorial: BlueprintNativeEvents Unreal Engine Community Wiki (unrealcommunity.wiki)](https://unrealcommunity.wiki/blueprints-empower-your-entire-team-with-blueprintnativeevents-x4fs54ut)