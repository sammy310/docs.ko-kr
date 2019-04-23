---
title: '방법: 컨트롤에 FocusVisualStyle 적용'
ms.date: 03/30/2017
helpviewer_keywords:
- properties [WPF], FocusVisualStyle
- FocusVisualStyle property [WPF]
ms.assetid: 363de99e-8ecc-438c-ac4a-f9147432ebd6
ms.openlocfilehash: 53d4984946143c15c4a2b71095529fb5ee7de4b1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59133551"
---
# <a name="how-to-apply-a-focusvisualstyle-to-a-control"></a><span data-ttu-id="84fd3-102">방법: 컨트롤에 FocusVisualStyle 적용</span><span class="sxs-lookup"><span data-stu-id="84fd3-102">How to: Apply a FocusVisualStyle to a Control</span></span>
<span data-ttu-id="84fd3-103">이 예제에서는 리소스에서 포커스 비주얼 스타일을 만들고 컨트롤에 스타일을 적용 하는 방법을 보여 줍니다.를 사용 하 여 <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="84fd3-103">This example shows you how to create a focus visual style in resources and apply the style to a control, using the <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="84fd3-104">예제</span><span class="sxs-lookup"><span data-stu-id="84fd3-104">Example</span></span>  
 <span data-ttu-id="84fd3-105">다음 예제에서는 만드는 추가 컨트롤 합성 컨트롤에 키보드에 포커스가 있을 때만 적용 되는 스타일을 정의 합니다 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="84fd3-105">The following example defines a style that creates additional control compositing that only applies when that control is keyboard focused in the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span></span> <span data-ttu-id="84fd3-106">사용 하 여 스타일을 정의 하 여 이렇게를 <xref:System.Windows.Controls.ControlTemplate>를 설정 하는 경우 리소스로 해당 스타일을 참조 하는 <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="84fd3-106">This is accomplished by defining a style with a <xref:System.Windows.Controls.ControlTemplate>, then referencing that style as a resource when setting the <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> property.</span></span>  
  
 <span data-ttu-id="84fd3-107">테두리와 같은 외부 영역을 사각형 영역 외부에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84fd3-107">An external rectangle resembling a border is placed outside of the rectangular area.</span></span> <span data-ttu-id="84fd3-108">스타일의 크기 조정을 사용 하 여 수정이 고, 그렇지 않으면 합니다 <xref:System.Windows.FrameworkElement.ActualHeight%2A> 및 <xref:System.Windows.FrameworkElement.ActualWidth%2A> 포커스 비주얼 스타일이 적용 되는 사각형 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="84fd3-108">Unless otherwise modified, the sizing of the style uses the <xref:System.Windows.FrameworkElement.ActualHeight%2A> and <xref:System.Windows.FrameworkElement.ActualWidth%2A> of the rectangular control where the focus visual style is applied.</span></span> <span data-ttu-id="84fd3-109">에 대해 음수 값을 설정 하는이 예제는 <xref:System.Windows.FrameworkElement.Margin%2A> 약간 포커스가 있는 컨트롤 외부에 테두리를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="84fd3-109">This example sets negative values for the <xref:System.Windows.FrameworkElement.Margin%2A> to make the border appear slightly outside the focused control.</span></span>  
  
 [!code-xaml[FEFocusVisualStyle#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEFocusVisualStyle/CS/page1.xaml#xaml)]  
  
 <span data-ttu-id="84fd3-110"><xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> 는 가산적 함께 제공 되는 모든 컨트롤 템플릿 스타일에 명시적 스타일 또는 테마 스타일;에서 컨트롤에 대 한 기본 스타일을 여전히 만들 수를 사용 하 여는 <xref:System.Windows.Controls.ControlTemplate> 스타일을 설정 하 고는 <xref:System.Windows.FrameworkElement.Style%2A> 속성.</span><span class="sxs-lookup"><span data-stu-id="84fd3-110">A <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> is additive to any control template style that comes either from an explicit style or a theme style; the primary style for a control can still be created by using a <xref:System.Windows.Controls.ControlTemplate> and setting that style to the <xref:System.Windows.FrameworkElement.Style%2A> property.</span></span>  
  
 <span data-ttu-id="84fd3-111">포커스 비주얼 스타일 테마 또는 UI를 일관 되 게 사용 해야 각 포커스 가능 요소에 대해 다른 이름을 사용 하는 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="84fd3-111">Focus visual styles should be used consistently across a theme or a UI, rather than using a different one for each focusable element.</span></span> <span data-ttu-id="84fd3-112">자세한 내용은 참조 하세요 [컨트롤에 FocusVisualStyle 포커스 스타일 지정](styling-for-focus-in-controls-and-focusvisualstyle.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="84fd3-112">For details, see [Styling for Focus in Controls, and FocusVisualStyle](styling-for-focus-in-controls-and-focusvisualstyle.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84fd3-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="84fd3-113">See also</span></span>

- <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>
- [<span data-ttu-id="84fd3-114">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="84fd3-114">Styling and Templating</span></span>](../controls/styling-and-templating.md)
- [<span data-ttu-id="84fd3-115">컨트롤의 포커스 스타일 지정 및 FocusVisualStyle</span><span class="sxs-lookup"><span data-stu-id="84fd3-115">Styling for Focus in Controls, and FocusVisualStyle</span></span>](styling-for-focus-in-controls-and-focusvisualstyle.md)
