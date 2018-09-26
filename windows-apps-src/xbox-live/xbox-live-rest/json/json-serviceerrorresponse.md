---
title: ServiceErrorResponse (JSON)
assetID: a2077df8-f76c-0233-8e41-68267b681862
permalink: en-us/docs/xboxlive/rest/json-serviceerrorresponse.html
author: KevinAsgari
description: " ServiceErrorResponse (JSON)"
ms.author: kevinasg
ms.date: 20-12-2017
ms.topic: article
ms.prod: windows
ms.technology: uwp
keywords: xbox live, xbox, 游戏, uwp, windows 10, xbox one
ms.localizationpriority: medium
ms.openlocfilehash: f0eed745b9350bd1bc2f4860cb3db5e5a6b9ad7c
ms.sourcegitcommit: e4f3e1b2d08a02b9920e78e802234e5b674e7223
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "4204408"
---
# <a name="serviceerrorresponse-json"></a>ServiceErrorResponse (JSON)
当遇到服务错误时，将返回一个相应的 HTTP 错误代码。 （可选），该服务还可能包括 ServiceErrorResponse 对象，如下面定义。 在生产环境中，可能会包含更少的数据。 
<a id="ID4EN"></a>

 
## <a name="serviceerrorresponse"></a>ServiceErrorResponse
 
ServiceErrorResponse 对象具有以下规范。
 
| 成员| 类型| 说明| 
| --- | --- | --- | 
| <b>错误代码</b>| 32 位有符号整数| 与错误 （可以为 null） 关联的代码。| 
| <b>errorMessage</b>| 字符串| 有关错误的其他详细信息。| 
  
<a id="ID4EVB"></a>

 
## <a name="sample-json-syntax"></a>JSON 语法示例
 

```json
{
   "errorCode": 8377,
   "errorMessage": "XUID specified in the claim does not match URI XUID."
 }
    
```

  
<a id="ID4E5B"></a>

 
## <a name="see-also"></a>另请参阅
 
<a id="ID4EAC"></a>

 
##### <a name="parent"></a>Parent 的子磁盘） 

[JavaScript 对象表示法 (JSON) 对象参考](atoc-xboxlivews-reference-json.md)

   