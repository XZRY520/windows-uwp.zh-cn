---
author: WilliamsJason
title: "Device Portal 文件夹上载 API 参考"
description: "了解如何以编程方式访问文件夹上载 API。"
ms.sourcegitcommit: fdc25fa4bd7bd5bfa598b993f23cd0ae9783dd0e
ms.openlocfilehash: 942ddc13b0deba382ad7758bc30bd9a5b0cceb11

---

# 将文件夹上载到开发目录

**请求**

你可以一次将整个文件夹上载到 DevelopmentFiles 的“已知文件夹 ID”（或上载到该文件中的子文件夹）。

方法      | 请求 URI
:------     | :------
POST | /api/app/packagemanager/upload 
<br />
**URI 参数**

你可以在请求 URI 上指定以下附加参数：

URI 参数      | 描述
:------     | :-----
destinationFolder（必需） | 要上载的文件夹的目标文件夹名称。 此文件夹将放置在主机的 d:\developmentfiles\LooseApps 之下。 如果此文件夹是 LooseApps 下面的一个子文件夹，那么该文件夹的名称应进行 base64 编码，因为它可能包含路径分隔符。
<br />

**请求标头**

- 无

**请求正文**

- 目录内容的多部分一致性 http 正文。

**响应**

**状态代码**

此 API 具有以下预期状态代码。

HTTP 状态代码      | 说明
:------     | :-----
200 | 成功
4XX | 错误代码
5XX | 错误代码
<br />
**可用设备系列**

* Windows Xbox




<!--HONumber=Jun16_HO4-->

