---
Description: 合作伙伴中心中的分级报表，可以查看客户如何评定您的应用程序存储区中。
title: 分级报告
ms.date: 10/31/2018
ms.topic: article
keywords: windows 10，uwp，评级，速率，星型，星评级
ms.localizationpriority: medium
ms.openlocfilehash: 9b507212cd660a025bc3d858fc2938cf59d4219f
ms.sourcegitcommit: b034650b684a767274d5d88746faeea373c8e34f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57640052"
---
# <a name="ratings-report"></a>分级报告


**分级**中的报表[合作伙伴中心](https://partner.microsoft.com/dashboard)，可以查看客户如何评定您的应用程序存储区中。 

可以在合作伙伴中心，查看此数据或[将报告下载](download-analytic-reports.md)要脱机查看。 或者，您可以以编程方式来检索此数据通过使用[获取的应用程序评论](../monetize/get-app-reviews.md)中的方法[Microsoft Store analytics REST API](../monetize/access-analytics-data-using-windows-store-services.md)。

> [!TIP]
> 若要快速查看最近 30 天中所有应用的评论、评分和用户反馈，请在左侧导航菜单中展开**参与**，然后选择**评论和反馈。** 

## <a name="apply-filters"></a>应用筛选器

在页面顶部附近，可以选择希望显示评论的时间段。 默认选择为**生命周期**，但可以选择显示 30 天、3 个月、6 个月或 12 个月的评论，或指定的自定义数据范围的评论。 请注意，**评分细目**和**按时间的平均评分**图将始终显示过去 12 个月的数据；这些时间期限选择将不会影响这些表格。

还可以展开**筛选器**以按下列选项筛选此页面上显示的评论。 这些筛选器将不适用于**评分细目**和**按时间的平均评分**图。

-   **市场**:默认设置是**所有市场**。 如果你希望此页面仅显示特定市场中客户的分级，你可以选择该市场。
-   **设备类型**:默认筛选器是**的所有设备**。 如果你希望此页面仅显示使用特定设备类型的客户留下的分级，你可以选择该设备类型。
-   **OS 版本**:默认设置是**所有**。 如果希望此页面以仅显示在该操作系统版本上的客户的评级左侧，可以选择某一特定 OS 版本。
-   **类别名称**:默认筛选器是**所有**。 可以选择以仅显示与评审我们已识别为属于特定相关联的分级[查看见解类别](reviews-report.md#insight-categories)以仅显示评审我们已与该类别相关联。 

> [!TIP]
> 如果看不到任何分级的页上，检查以确保您的筛选器未排除所有您的分级。 例如，如果您按您的应用程序不支持目标 OS 进行筛选，不会看到任何分级。


## <a name="rating-breakdown"></a>分级细分

**分级细分**图表所示： 
- 应用的平均星级评分。
- 过去 12 个月中应用的评分总数。
- 每个星级评分的评分总数。
- 过去 12 个月中每个星级评分中每种评分类型（新评分或修改后评分）的评分总数。
 - **新评分**是客户已提交但未进行任何更改的评分。
 - **修改后评分**是客户以任何方式进行更改的评分，包括仅更改评论的文本。

> [!TIP]
> 客户在应用商店中看到的平均评分会考虑客户的市场和设备类型，因此可能不同于在此报告中看到的内容。


## <a name="average-rating"></a>平均分级

**平均评分**图表显示了如何应用的平均级别已更改在过去的 12 个月。

而不是在过去的 12 个月过程中计算所有分级左侧的平均值 (如**分级细分**图表)，则**平均评分**图表显示客户如何在给定一周的分级应用。 这有助于确认趋势，或确定评分是否受到更新或其他因素的影响。

## <a name="rating-by-market"></a>按市场的评级

**评级按市场**图表通过所选时段内每个市场中显示平均分级的细分。 默认情况下，我们显示此数据在视觉对象**地图**窗体，但您还可以切换以查看其作为在右上角中的控件**表**。

**表**视图来显示五个市场了一次，并按字母顺序或最大/最小平均评分排序。 此外可以下载此图表的数据一起查看适用于所有市场信息。

你还可以筛选此图**评级**。 默认情况下检查评审与所有星来评分，但您可以选中和取消选中特定评级 （从 1 到 5 星)，如果你想要仅查看与特定的星级相关联的评论。