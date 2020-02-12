---
title: '방법: 요소의 높이 속성 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- height properties [WPF]
- Panel control [WPF], height properties of elements
ms.assetid: 5ab9e781-dbb8-469a-a3c8-cf38ce312647
ms.openlocfilehash: 6500af3c637092820e538d79894d600d617953bf
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124288"
---
# <a name="how-to-set-the-height-properties-of-an-element"></a><span data-ttu-id="524c5-102">방법: 요소의 높이 속성 설정</span><span class="sxs-lookup"><span data-stu-id="524c5-102">How to: Set the Height Properties of an Element</span></span>
## <a name="example"></a><span data-ttu-id="524c5-103">예제</span><span class="sxs-lookup"><span data-stu-id="524c5-103">Example</span></span>  
 <span data-ttu-id="524c5-104">이 예제에서는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서 4 개의 높이 관련 속성 간의 렌더링 동작 차이를 시각적으로 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="524c5-104">This example visually shows the differences in rendering behavior among the four height-related properties in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span>  
  
 <span data-ttu-id="524c5-105"><xref:System.Windows.FrameworkElement> 클래스는 요소의 높이 특성을 설명 하는 네 가지 속성을 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="524c5-105">The <xref:System.Windows.FrameworkElement> class exposes four properties that describe the height characteristics of an element.</span></span> <span data-ttu-id="524c5-106">이러한 네 가지 속성은 충돌할 수 있으며, 그에 따라 우선 순위를 설정 하는 값은 다음과 같이 결정 됩니다. <xref:System.Windows.FrameworkElement.MinHeight%2A> 값이 <xref:System.Windows.FrameworkElement.MaxHeight%2A> 값 보다 우선 하므로 <xref:System.Windows.FrameworkElement.Height%2A> 값 보다 우선적으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="524c5-106">These four properties can conflict, and when they do, the value that takes precedence is determined as follows: the <xref:System.Windows.FrameworkElement.MinHeight%2A> value takes precedence over the <xref:System.Windows.FrameworkElement.MaxHeight%2A> value, which in turn takes precedence over the <xref:System.Windows.FrameworkElement.Height%2A> value.</span></span> <span data-ttu-id="524c5-107">네 번째 속성인 <xref:System.Windows.FrameworkElement.ActualHeight%2A>은 읽기 전용 이며 레이아웃 프로세스와의 상호 작용에 따라 결정 되는 실제 높이를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="524c5-107">A fourth property, <xref:System.Windows.FrameworkElement.ActualHeight%2A>, is read-only, and reports the actual height as determined by interactions with the layout process.</span></span>  
  
 <span data-ttu-id="524c5-108">다음 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 예제에서는 <xref:System.Windows.Shapes.Rectangle> 요소 (`rect1`)를 <xref:System.Windows.Controls.Canvas>의 자식으로 그립니다.</span><span class="sxs-lookup"><span data-stu-id="524c5-108">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] examples draw a <xref:System.Windows.Shapes.Rectangle> element (`rect1`) as a child of <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="524c5-109"><xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>및 <xref:System.Windows.FrameworkElement.Height%2A>의 속성 값을 나타내는 일련의 <xref:System.Windows.Controls.ListBox> 요소를 사용 하 여 <xref:System.Windows.Shapes.Rectangle>의 높이 속성을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="524c5-109">You can change the height properties of a <xref:System.Windows.Shapes.Rectangle> by using a series of <xref:System.Windows.Controls.ListBox> elements that represent the property values of <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>, and <xref:System.Windows.FrameworkElement.Height%2A>.</span></span> <span data-ttu-id="524c5-110">이러한 방식으로 각 속성의 우선 순위가 시각적으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="524c5-110">In this manner, the precedence of each property is visually displayed.</span></span>  
  
 [!code-xaml[HeightMinHeightMaxHeight#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#1)]  
[!code-xaml[HeightMinHeightMaxHeight#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="524c5-111">다음 코드 예제에서는 <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> 이벤트에서 발생 하는 이벤트를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="524c5-111">The following code-behind examples handle the events that the <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event raises.</span></span> <span data-ttu-id="524c5-112">각 처리기는 <xref:System.Windows.Controls.ListBox>의 입력을 사용 하 고, 값을 <xref:System.Double>로 구문 분석 하 고, 값을 지정 된 높이 관련 속성에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="524c5-112">Each handler takes the input from the <xref:System.Windows.Controls.ListBox>, parses the value as a <xref:System.Double>, and applies the value to the specified height-related property.</span></span> <span data-ttu-id="524c5-113">높이 값도 문자열로 변환 되 고 다양 한 <xref:System.Windows.Controls.TextBlock> 요소에 기록 됩니다 (해당 요소의 정의는 선택한 XAML에 표시 되지 않음).</span><span class="sxs-lookup"><span data-stu-id="524c5-113">The height values are also converted to a string and written to various <xref:System.Windows.Controls.TextBlock> elements (definition of those elements is not shown in the selected XAML).</span></span>  
  
 [!code-csharp[HeightMinHeightMaxHeight#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml.cs#3)]
 [!code-vb[HeightMinHeightMaxHeight#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HeightMinHeightMaxHeight/VisualBasic/Window1.xaml.vb#3)]  
  
 <span data-ttu-id="524c5-114">전체 샘플은 [Height 속성 샘플](https://github.com/microsoft/WPF-Samples/tree/master/Elements/HeightProperties)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="524c5-114">For the complete sample, see [Height Properties Sample](https://github.com/microsoft/WPF-Samples/tree/master/Elements/HeightProperties).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="524c5-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="524c5-115">See also</span></span>

- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.FrameworkElement.ActualHeight%2A>
- <xref:System.Windows.FrameworkElement.MaxHeight%2A>
- <xref:System.Windows.FrameworkElement.MinHeight%2A>
- <xref:System.Windows.FrameworkElement.Height%2A>
- [<span data-ttu-id="524c5-116">요소의 너비 속성 설정</span><span class="sxs-lookup"><span data-stu-id="524c5-116">Set the Width Properties of an Element</span></span>](how-to-set-the-width-properties-of-an-element.md)
- [<span data-ttu-id="524c5-117">패널 개요</span><span class="sxs-lookup"><span data-stu-id="524c5-117">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="524c5-118">Height 속성 샘플</span><span class="sxs-lookup"><span data-stu-id="524c5-118">Height Properties Sample</span></span>](https://github.com/microsoft/WPF-Samples/tree/master/Elements/HeightProperties)
