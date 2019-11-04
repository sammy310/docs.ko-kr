---
title: '방법: 컨트롤에 FocusVisualStyle 적용'
ms.date: 03/30/2017
helpviewer_keywords:
- properties [WPF], FocusVisualStyle
- FocusVisualStyle property [WPF]
ms.assetid: 363de99e-8ecc-438c-ac4a-f9147432ebd6
ms.openlocfilehash: b44330ee7554f953389556bd62ff49db120b5db9
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459812"
---
# <a name="how-to-apply-a-focusvisualstyle-to-a-control"></a><span data-ttu-id="c3741-102">방법: 컨트롤에 FocusVisualStyle 적용</span><span class="sxs-lookup"><span data-stu-id="c3741-102">How to: Apply a FocusVisualStyle to a Control</span></span>
<span data-ttu-id="c3741-103">이 예제에서는 <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> 속성을 사용 하 여 리소스에서 포커스 비주얼 스타일을 만들고 컨트롤에 스타일을 적용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c3741-103">This example shows you how to create a focus visual style in resources and apply the style to a control, using the <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c3741-104">예제</span><span class="sxs-lookup"><span data-stu-id="c3741-104">Example</span></span>  
 <span data-ttu-id="c3741-105">다음 예제에서는 해당 컨트롤이 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]에 포커스가 있는 경우에만 적용 되는 추가 컨트롤 합성을 만드는 스타일을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3741-105">The following example defines a style that creates additional control compositing that only applies when that control is keyboard focused in the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span></span> <span data-ttu-id="c3741-106">이렇게 하려면 <xref:System.Windows.Controls.ControlTemplate>를 사용 하 여 스타일을 정의한 다음 <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> 속성을 설정할 때 해당 스타일을 리소스로 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3741-106">This is accomplished by defining a style with a <xref:System.Windows.Controls.ControlTemplate>, then referencing that style as a resource when setting the <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> property.</span></span>  
  
 <span data-ttu-id="c3741-107">테두리와 유사한 외부 사각형이 사각형 영역 외부에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3741-107">An external rectangle resembling a border is placed outside of the rectangular area.</span></span> <span data-ttu-id="c3741-108">달리 수정 하지 않는 한 스타일의 크기 조정에서는 포커스 비주얼 스타일이 적용 되는 사각형 컨트롤의 <xref:System.Windows.FrameworkElement.ActualHeight%2A> 및 <xref:System.Windows.FrameworkElement.ActualWidth%2A>을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3741-108">Unless otherwise modified, the sizing of the style uses the <xref:System.Windows.FrameworkElement.ActualHeight%2A> and <xref:System.Windows.FrameworkElement.ActualWidth%2A> of the rectangular control where the focus visual style is applied.</span></span> <span data-ttu-id="c3741-109">이 예제에서는 <xref:System.Windows.FrameworkElement.Margin%2A>에 대해 음수 값을 설정 하 여 테두리가 포커스가 지정 된 컨트롤의 바깥쪽에 약간 표시 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3741-109">This example sets negative values for the <xref:System.Windows.FrameworkElement.Margin%2A> to make the border appear slightly outside the focused control.</span></span>  
  
 [!code-xaml[FEFocusVisualStyle#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEFocusVisualStyle/CS/page1.xaml#xaml)]  
  
 <span data-ttu-id="c3741-110"><xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> 명시적 스타일 또는 테마 스타일에서 제공 되는 모든 컨트롤 템플릿 스타일에 추가 됩니다. <xref:System.Windows.Controls.ControlTemplate>를 사용 하 고 해당 스타일을 <xref:System.Windows.FrameworkElement.Style%2A> 속성으로 설정 하 여 컨트롤의 기본 스타일을 계속 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3741-110">A <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> is additive to any control template style that comes either from an explicit style or a theme style; the primary style for a control can still be created by using a <xref:System.Windows.Controls.ControlTemplate> and setting that style to the <xref:System.Windows.FrameworkElement.Style%2A> property.</span></span>  
  
 <span data-ttu-id="c3741-111">포커스 비주얼 스타일은 포커스를 받을 수 있는 각 요소에 대해 서로 다른 항목을 사용 하는 대신 테마 또는 UI에서 일관 되 게 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3741-111">Focus visual styles should be used consistently across a theme or a UI, rather than using a different one for each focusable element.</span></span> <span data-ttu-id="c3741-112">자세한 내용은 [컨트롤의 포커스 스타일 지정 및 FocusVisualStyle](styling-for-focus-in-controls-and-focusvisualstyle.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c3741-112">For details, see [Styling for Focus in Controls, and FocusVisualStyle](styling-for-focus-in-controls-and-focusvisualstyle.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3741-113">참조</span><span class="sxs-lookup"><span data-stu-id="c3741-113">See also</span></span>

- <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>
- [<span data-ttu-id="c3741-114">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="c3741-114">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="c3741-115">컨트롤의 포커스 스타일 지정 및 FocusVisualStyle</span><span class="sxs-lookup"><span data-stu-id="c3741-115">Styling for Focus in Controls, and FocusVisualStyle</span></span>](styling-for-focus-in-controls-and-focusvisualstyle.md)
