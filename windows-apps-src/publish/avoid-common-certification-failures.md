---
Description: 查看此列表以帮助避免频繁地阻止应用通过认证的问题，或者在发布应用后，可能在点检查过程中标识的问题。
title: 避免常见的认证失败
ms.assetid: 9E9E3841-2F9B-42D4-B5F8-4C7C31E42E3D
ms.date: 10/31/2018
ms.topic: article
keywords: windows 10, uwp
ms.localizationpriority: medium
ms.openlocfilehash: 0032a5bbaafabab3c847b2b7c48536873f4532dd
ms.sourcegitcommit: 978df7dfd3813de51609b6a44aedcd402083a5fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2019
ms.locfileid: "66826165"
---
# <a name="avoid-common-certification-failures"></a>避免常见的认证失败


查看此列表以帮助避免频繁地阻止应用通过认证的问题，或者在发布应用后，可能在点检查过程中标识的问题。

> [!NOTE]
> 请确保查看[Microsoft Store 策略](store-policies.md)以确保您的应用程序满足所有列出的要求。

-   仅在应用完成时提交你的应用。 欢迎使用你的应用提要来介绍即将推出的功能，但是请确保你的应用不包含未完成的部分、指向正在构建的网页的链接，或者其他任何会让客户觉得你的应用不完整的内容。

-   在提交应用前[使用 Windows 应用认证工具包测试应用](../debug-test-perf/windows-app-certification-kit.md)。

-   在多个不同配置上测试你的应用，以尽可能确保应用稳定。

-   确保你的应用在没有网络连接时不会崩溃。 即使您的应用需要连接网络才能实际使用，也应该能够在没有网络连接的情况下适当运行。

-   提供使用你的应用时所需的[任何必要信息](notes-for-certification.md)，例如，如果应用要求用户登录某项服务，则需要提供测试帐户的用户名和密码；还可能需要说明访问隐藏的功能或锁定的功能所需的任何步骤。

-   包括[隐私策略 URL](enter-app-properties.md#privacy-policy-url)如果您的应用程序需要一个; 例如，如果您的应用程序访问任何类型的个人信息以任何方式或者另外法律要求。 若要帮助确定您的应用程序是否需要隐私策略，请查看[应用程序开发人员协议](https://docs.microsoft.com/legal/windows/agreements/app-developer-agreement)并[Microsoft Store 策略](store-policies.md)。

-   请确保您的应用的说明清晰地展示您的应用的用途。 有关帮助，请参阅[编写出色的应用说明](write-a-great-app-description.md)中提供的相关指南。

-   针对[年龄分级](age-ratings.md)部分中的所有问题提供完整并且准确无误的答案。

-   除非你已经进行专门的工程处理和测试，确定了应用适用于辅助功能方案，否则不要[将应用声明为辅助应用](product-declarations.md#this-app-has-been-tested-to-meet-accessibility-guidelines)。

-   如果你的应用使用来自 [**Windows.ApplicationModel.Store**](https://docs.microsoft.com/uwp/api/Windows.ApplicationModel.Store) 命名空间的商用 API，请确保对应用进行测试并验证它是否可处理常见的异常情况。 此外，请确保你的应用使用 [**CurrentApp**](https://docs.microsoft.com/uwp/api/Windows.ApplicationModel.Store.CurrentApp) 类（而非 [**CurrentAppSimulator**](https://docs.microsoft.com/uwp/api/Windows.ApplicationModel.Store.CurrentAppSimulator) 类，该类仅用于测试）。 （请注意，如果你的应用面向 Windows 10 版本 1607 或更高版本，我们建议使用 [Windows.Services.Store](https://docs.microsoft.com/uwp/api/windows.services.store) 命名空间的成员，而非使用 Windows.ApplicationModel.Store 命名空间。）


 

 




