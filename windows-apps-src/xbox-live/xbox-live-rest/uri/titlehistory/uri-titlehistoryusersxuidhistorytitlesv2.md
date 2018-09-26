---
title: /users/xuid({xuid})/history/titles
assetID: 2f8eb79a-42c2-0267-cbf2-8682bb28f270
permalink: en-us/docs/xboxlive/rest/uri-titlehistoryusersxuidhistorytitlesv2.html
author: KevinAsgari
description: " /users/xuid({xuid})/history/titles"
ms.author: kevinasg
ms.date: 20-12-2017
ms.topic: article
ms.prod: windows
ms.technology: uwp
keywords: xbox live, xbox, 游戏, uwp, windows 10, xbox one
ms.localizationpriority: medium
ms.openlocfilehash: a4780c92fc16adb697783ecee50d36523ff92998
ms.sourcegitcommit: 232543fba1fb30bb1489b053310ed6bd4b8f15d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "4177507"
---
# <a name="usersxuidxuidhistorytitles"></a>/users/xuid({xuid})/history/titles
 
此通用资源标识符 (URI) 提供对用户的成就相关游戏历史记录访问。
 
这些 Uri 的域是`achievements.xboxlive.com`。
 
<a id="ID4E1"></a>

 
## <a name="uri-parameters"></a>URI 参数
 
| 参数| 类型| 说明| 
| --- | --- | --- | 
| xuid| 64 位无符号的整数| Xbox 用户 ID (XUID) 所访问其游戏历史记录的用户。| 
  
<a id="ID4EAC"></a>

 
## <a name="valid-methods"></a>有效的方法

[GET](uri-titlehistoryusersxuidhistorytitlesgetv2.md)

&nbsp;&nbsp;获取的游戏的用户已解锁或对其成就进度的列表。 此 API 不会返回游戏播放或启动的用户的完整历史记录。
 
<a id="ID4EKC"></a>

 
## <a name="see-also"></a>另请参阅
 
<a id="ID4EMC"></a>

 
##### <a name="parent"></a>Parent 的子磁盘） 

[游戏成就历史记录 URI](atoc-reference-titlehistoryv2.md)

   