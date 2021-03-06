---
title: 导航入门
description: 导航入门
ms.assetid: F4DF5C5F-C886-4483-BBDA-498C4E2C1BAF
ms.date: 02/08/2017
ms.topic: article
keywords: windows 10, uwp
ms.localizationpriority: medium
ms.openlocfilehash: dcbc8f6737c2b7450e42ed01a752087d6e9034c1
ms.sourcegitcommit: b52ddecccb9e68dbb71695af3078005a2eb78af1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/20/2019
ms.locfileid: "74259151"
---
# <a name="getting-started-navigation"></a>入门：导航


## <a name="adding-navigation"></a>添加导航

iOS 提供 **UINavigationController** 类以帮助应用内导航：可按下和弹出视图，以创建定义应用的**UIViewControllers**层次结构。

与此相反，包含多个视图的 Windows 10 应用程序需要更多的网站导航方法。 想象一下，用户在单击控件以其自己的方式浏览应用时，在页面间来回跳跃。 有关详细信息，请参阅[导航设计基础知识](https://docs.microsoft.com/windows/uwp/layout/navigation-basics)。

在 Windows 10 应用中管理此导航的一种方法是使用[**Frame**](https://docs.microsoft.com/uwp/api/Windows.UI.Xaml.Controls.Frame)类。 下面的演练向你展示如何尝试执行此操作。

继续使用之前启动的解决方案，打开 **MainPage.xaml** 文件，然后在 **“设计”** 视图中添加按钮。 将该按钮的 **Content** 属性从“Button”更改为“Go To Page”。 然后为按钮的 **Click** 事件创建一个处理程序，如下图所示。 如果忘记了如何执行此操作，可回顾之前部分中的操作实例（提示：双击 **“设计”** 视图中的按钮）。

![在 Visual Studio 中添加按钮及其 Click 事件](images/ios-to-uwp/vs-go-to-page.png)

让我们添加新页面。 在 **“解决方案”** 视图中，点击 **“项目”** 菜单，然后点击 **“添加新项”** 。 如下图所示点击 **“空白页”** ，然后点击 **“添加”** 。

![在 Visual Studio 中添加新页面](images/ios-to-uwp/vs-add-new-page.png)

接下来，向 BlankPage.xaml 文件中添加一个按钮。 我们可以使用 AppBarButton 控件并为它添加一个返回箭头图像：在 **“XAML”** 视图中，在 ` <AppBarButton Icon="Back"/>` 元素之间添加 `<Grid> </Grid>`。

现在，让我们向该按钮添加一个事件处理程序：在 "**设计**" 视图中双击该控件，然后 Microsoft Visual Studio 将文本 "AppBarButton\_单击" 添加到**单击**框（如下图所示），然后在 BlankPage.xaml.cs 文件中添加并显示相应的事件处理程序。

![在 Visual Studio 中添加一个后退按钮及其 Click 事件](images/ios-to-uwp/vs-add-back-button.png)

如果返回到 BlankPage.xaml 文件的 **XAML** 视图，`<AppBarButton>` 元素的 Extensible Application Markup Language (XAML) 代码现在应该与以下内容类似：

` <AppBarButton Icon="Back" Click="AppBarButton_Click"/>`

返回到 BlankPage.xaml.cs 文件，并添加此代码以便在用户点击该按钮后转到上一页。

```csharp
private void AppBarButton_Click(object sender, RoutedEventArgs e)
{
    // Add the following line of code.    
    Frame.GoBack();
}
```

最后，打开 MainPage.xaml.cs 文件并添加此代码。 在用户点击该按钮之后，它将打开 BlankPage。

```csharp
private void Button_Click(object sender, RoutedEventArgs e)
{
    // Add the following line of code.
    Frame.Navigate(typeof(BlankPage1));
}
```

现在运行该程序。 点击“Go To Page”按钮以转到另一页，然后点击后退箭头按钮返回到上一页。

页面导航由 [**Frame**](https://docs.microsoft.com/uwp/api/Windows.UI.Xaml.Controls.Frame) 类管理。 由于 iOS 中的**UINavigationController**类使用**pushViewController**和**popViewController**方法，因此 UWP 应用的**Frame**类提供了[**导航**](https://docs.microsoft.com/uwp/api/windows.ui.xaml.controls.frame.navigate)和[**GoBack**](https://docs.microsoft.com/uwp/api/windows.ui.xaml.controls.frame.goback)方法。 **Frame** 类还有一个名为 [**GoForward**](https://docs.microsoft.com/uwp/api/windows.ui.xaml.controls.frame.goforward) 的方法，该方法可以执行可能需要的操作。

此演练在每次导航到 BlankPage 时都会创建它的一个新实例。 （上一实例将被释放或自动*释放*）。 如果不希望每次都创建一个新实例，可将以下代码添加到 BlankPage.xaml.cs 文件中 BlankPage 类的构造函数。 这将启用 [**NavigationCacheMode**](https://docs.microsoft.com/uwp/api/windows.ui.xaml.controls.page.navigationcachemode) 行为。

```csharp
public BlankPage()
{
    this.InitializeComponent();
    // Add the following line of code.
    this.NavigationCacheMode = Windows.UI.Xaml.Navigation.NavigationCacheMode.Enabled;
}
```

你还可以获取或设置 **Frame** 类的 [**CacheSize**](https://docs.microsoft.com/uwp/api/windows.ui.xaml.controls.frame.cachesize) 属性，以管理在导航历史记录中可以缓存多少页面。

有关导航的详细信息，请参阅[导航](https://docs.microsoft.com/windows/uwp/layout/navigation-basics)和 [XAML 个性化动画示例](https://code.msdn.microsoft.com/windowsapps/Personality-Animations-3f857919)。

**请注意**  有关使用 JAVASCRIPT 和 HTML 的 UWP 应用的导航的信息，请参阅[快速入门：使用单页导航](https://docs.microsoft.com/previous-versions/windows/apps/hh452768(v=win.10))。
 
### <a name="next-step"></a>下一步

[入门：动画](getting-started-animation.md)

