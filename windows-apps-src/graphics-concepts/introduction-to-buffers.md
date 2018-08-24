---
title: 缓冲区简介
description: 缓冲区资源是一系列完全类型化的数据，被分组到元素中。
ms.assetid: 494FDF57-0FBE-434C-B568-06F977B40263
keywords:
- 缓冲区简介
author: michaelfromredmond
ms.author: mithom
ms.date: 02/08/2017
ms.topic: article
ms.prod: windows
ms.technology: uwp
ms.localizationpriority: medium
ms.openlocfilehash: 677eea4757220320bc364fef20bf5a5c8d4daaa2
ms.sourcegitcommit: 897a111e8fc5d38d483800288ad01c523e924ef4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2018
ms.locfileid: "1044336"
---
# <a name="introduction-to-buffers"></a>缓冲区简介


缓冲区资源是一系列完全类型化的数据，被分组到元素中。 缓冲区将存储数据，如*顶点缓冲区* 中的纹理坐标、*索引缓冲区* 中的索引、*常量缓冲区* 中的着色器常量数据、位置矢量、法向矢量或设备状态。

缓冲区元素是 1 到 4 组件组成。 缓冲区元素可以包含打包数据值（如 R8G8B8A8 表面值）、单个 8 位整数或四个 32 位浮点值。

缓冲区是作为非结构化资源创建的。 因为它是非结构化，缓冲区不能包含任何级别，无法获取筛选读取时，以及它不能为多级采样。

## <a name="span-idbuffertypesspanspan-idbuffertypesspanspan-idbuffertypesspanbuffer-types"></a><span id="Buffer_Types"></span><span id="buffer_types"></span><span id="BUFFER_TYPES"></span>缓冲区类型


以下是支持 Direct3D 11 的缓冲区资源类型。

-   [顶点缓冲区](#vertex-buffer)
-   [索引缓冲区](#index-buffer)
-   [常量缓冲区](#shader-constant-buffer)

### <a name="span-idvertexbufferspanspan-idvertexbufferspanspan-idvertexbufferspanspan-idvertex-bufferspanvertex-buffer"></a><span id="Vertex_Buffer"></span><span id="vertex_buffer"></span><span id="VERTEX_BUFFER"></span><span id="vertex-buffer"></span>顶点缓冲区

顶点缓冲区包含用于定义您的 geometry 的顶点数据。 顶点数据包括位置坐标、颜色数据、纹理坐标数据、法线数据等。

顶点缓冲区的最简单示例是一个仅包含位置数据。 它可进行可视化，如下图所示。

![包含位置数据的顶点缓冲区的图示](images/d3d10-resources-single-element-vb2.png)

更常见的情况是，顶点缓冲区包含完全指定 3D 顶点所需的所有数据。 示例可能是包含每顶点位置、法线和纹理坐标的顶点缓冲区。 此数据通常组织为每顶点元素集，如下图所示。

![包含位置、法线和纹理数据的顶点缓冲区的图示](images/d3d10-vertex-buffer-element.png)

此顶点缓冲区包含每个顶点数据;每个顶点存储三个元素 （位置、 普通、 和纹理坐标）。 通常，使用 3 个 32 位浮点指定每个位置和法线，使用两个 32 位浮点指定纹理坐标。

从顶点缓冲区访问数据，您需要知道哪些顶点访问，以及以下额外缓冲区参数：

-   Offset - 缓冲区起点到第一个顶点数据之间的字节数。
-   BaseVertexLocation - 从偏移到相应的绘图调用所使用的第一个顶点之间的字节数。

创建顶点缓冲区之前，您需要定义其布局。 创建的输入版式对象后，您可以将其绑定到[输入汇编 (IA) 阶段](input-assembler-stage--ia-.md)。

### <a name="span-idindexbufferspanspan-idindexbufferspanspan-idindexbufferspanspan-idindex-bufferspanindex-buffer"></a><span id="Index_Buffer"></span><span id="index_buffer"></span><span id="INDEX_BUFFER"></span><span id="index-buffer"></span>索引缓冲区

索引缓冲区顶点缓冲区到包含整数偏移量，以及用于更有效地呈现基元。 索引缓冲区包含一组连续的 16 位或 32 位索引；每个索引用于标识顶点缓冲区中的一个顶点。 索引缓冲区可进行可视化，如下图所示。

![索引缓冲区的图示](images/d3d10-index-buffer.png)

使用以下参数查找存储在索引缓冲区中的连续索引：

-   偏移量-从索引缓冲区的基址的字节数。
-   StartIndexLocation-指定第一个索引缓冲区元素从基本地址和偏移量。 开始位置表示要呈现的第一个索引。
-   IndexCount - 要呈现的索引的数量。

开始的索引缓冲区 = 索引缓冲区基址 + 偏移量 （字节） + StartIndexLocation \ * ElementSize （字节）;

在此计算，ElementSize 是每个索引缓冲区元素，后者是两个或四个字节的大小。

### <a name="span-idshaderconstantbufferspanspan-idshaderconstantbufferspanspan-idshaderconstantbufferspanspan-idshader-constant-bufferspanconstant-buffer"></a><span id="Shader_Constant_Buffer"></span><span id="shader_constant_buffer"></span><span id="SHADER_CONSTANT_BUFFER"></span><span id="shader-constant-buffer"></span>常量缓冲区

常量缓冲区可以有效地提供着色常量数据到管道。 您可以使用常量缓冲区存储流输出阶段的结果。 从概念上讲，常量缓冲区类似于单元素顶点缓冲区，只需将下图中所示。

![着色器-常量缓冲区的图示](images/d3d10-shader-resource-buffer.png)

每个元素存储 1 到 4 个组件常量（由所存储数据的格式决定）。

常量缓冲区可以仅使用单个绑定标志，但这不能使用任何其他绑定标志组合。

若要从着色读取着色器常量缓冲区，使用 HLSL 负载函数。 每个着色器阶段允许最多 15 个着色器-常量缓冲区；每个缓冲区可包含最多 4096 个常量。

## <a name="span-idrelated-topicsspanrelated-topics"></a><span id="related-topics"></span>相关主题


[顶点和索引缓冲区](vertex-and-index-buffers.md)

 

 



