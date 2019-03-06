---
title: '방법: ToolBar 컨트롤의 스타일 지정'
ms.date: 03/30/2017
helpviewer_keywords:
- styling controls on toolbar [WPF]
- toolbars [WPF]
- customizing controls on toolbar [WPF]
ms.assetid: ba6ae056-d6a9-4c24-90f8-467ab0bc0b1a
ms.openlocfilehash: d81aa227eb1ffcb3dbaa119c41d561cbb066b704
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364452"
---
# <a name="how-to-style-controls-on-a-toolbar"></a><span data-ttu-id="e2b16-102">방법: ToolBar 컨트롤의 스타일 지정</span><span class="sxs-lookup"><span data-stu-id="e2b16-102">How to: Style Controls on a ToolBar</span></span>
<span data-ttu-id="e2b16-103">합니다 <xref:System.Windows.Controls.ToolBar> 정의 <xref:System.Windows.ResourceKey> 내에서 컨트롤의 스타일을 지정 하는 개체는 <xref:System.Windows.Controls.ToolBar>합니다.</span><span class="sxs-lookup"><span data-stu-id="e2b16-103">The <xref:System.Windows.Controls.ToolBar> defines <xref:System.Windows.ResourceKey> objects to specify the style of controls within the <xref:System.Windows.Controls.ToolBar>.</span></span>  <span data-ttu-id="e2b16-104">컨트롤에 스타일을 지정 하는 <xref:System.Windows.Controls.ToolBar>설정를 `x:key` 스타일의 특성을 <xref:System.Windows.ResourceKey> 에 정의 된 <xref:System.Windows.Controls.ToolBar>합니다.</span><span class="sxs-lookup"><span data-stu-id="e2b16-104">To style a control in a <xref:System.Windows.Controls.ToolBar>, set the `x:key` attribute of the style to a <xref:System.Windows.ResourceKey> defined in <xref:System.Windows.Controls.ToolBar>.</span></span>  
  
 <span data-ttu-id="e2b16-105">합니다 <xref:System.Windows.Controls.ToolBar> 정의 다음 <xref:System.Windows.ResourceKey> 개체:</span><span class="sxs-lookup"><span data-stu-id="e2b16-105">The <xref:System.Windows.Controls.ToolBar> defines the following <xref:System.Windows.ResourceKey> objects:</span></span>  
  
-   <xref:System.Windows.Controls.ToolBar.ButtonStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.CheckBoxStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.ComboBoxStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.MenuStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.RadioButtonStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.SeparatorStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.TextBoxStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.ToggleButtonStyleKey%2A>  
  
## <a name="example"></a><span data-ttu-id="e2b16-106">예제</span><span class="sxs-lookup"><span data-stu-id="e2b16-106">Example</span></span>  
 <span data-ttu-id="e2b16-107">다음 예제에서는 정의 내에서 컨트롤에 대 한 스타일을 <xref:System.Windows.Controls.ToolBar>입니다.</span><span class="sxs-lookup"><span data-stu-id="e2b16-107">The following example defines styles for the controls within a <xref:System.Windows.Controls.ToolBar>.</span></span>  
  
 [!code-xaml[ToolBar_snip#ToolBarAllStyles](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolBar_snip/CS/pane1.xaml#toolbarallstyles)]  
[!code-xaml[ToolBar_snip#ToolBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolBar_snip/CS/pane1.xaml#toolbar)]  
  
## <a name="see-also"></a><span data-ttu-id="e2b16-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="e2b16-108">See also</span></span>
- [<span data-ttu-id="e2b16-109">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="e2b16-109">Styling and Templating</span></span>](styling-and-templating.md)
