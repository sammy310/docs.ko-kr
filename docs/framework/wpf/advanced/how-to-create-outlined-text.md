---
title: '방법: 윤곽선이 있는 텍스트 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- typography [WPF], linear gradient brush
- outlined text [WPF]
- gradient brush [WPF]
- linear gradient brush [WPF]
- typography [WPF], outline effects
ms.assetid: 4aa3cf6e-1953-4f26-8230-7c1409e5f28d
ms.openlocfilehash: d0ce46b9895589fd4635b567136204368a6431ad
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186866"
---
# <a name="how-to-create-outlined-text"></a><span data-ttu-id="816ae-102">방법: 윤곽선이 있는 텍스트 만들기</span><span class="sxs-lookup"><span data-stu-id="816ae-102">How to: Create Outlined Text</span></span>
<span data-ttu-id="816ae-103">대부분의 경우 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 응용 프로그램의 텍스트 문자열에 장식을 추가할 때 개별 문자 또는 문자 모음의 집합측면에서 텍스트를 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="816ae-103">In most cases, when you are adding ornamentation to text strings in your [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application, you are using text in terms of a collection of discrete characters, or glyphs.</span></span> <span data-ttu-id="816ae-104">예를 들어 선형 그라데이션 브러시를 만들어 오브젝트의 속성에 <xref:System.Windows.Controls.Control.Foreground%2A> 적용할 수 있습니다. <xref:System.Windows.Controls.TextBox></span><span class="sxs-lookup"><span data-stu-id="816ae-104">For example, you could create a linear gradient brush and apply it to the <xref:System.Windows.Controls.Control.Foreground%2A> property of a <xref:System.Windows.Controls.TextBox> object.</span></span> <span data-ttu-id="816ae-105">텍스트 상자를 표시하거나 편집하면 선형 그라데이션 브러시가 텍스트 문자열의 현재 문자 집합에 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="816ae-105">When you display or edit the text box, the linear gradient brush is automatically applied to the current set of characters in the text string.</span></span>  
  
 ![선형 그라데이션 브러시로 표시된 텍스트](./media/how-to-create-outlined-text/text-linear-gradient.jpg)
  
 <span data-ttu-id="816ae-107">그러나 텍스트를 개체로 <xref:System.Windows.Media.Geometry> 변환하여 시각적으로 풍부한 다른 유형의 텍스트를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="816ae-107">However, you can also convert text into <xref:System.Windows.Media.Geometry> objects, allowing you to create other types of visually rich text.</span></span> <span data-ttu-id="816ae-108">예를 들어 텍스트 문자열의 윤곽선을 기반으로 <xref:System.Windows.Media.Geometry> 개체를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="816ae-108">For example, you could create a <xref:System.Windows.Media.Geometry> object based on the outline of a text string.</span></span>  
  
 ![선형 그라데이션 브러시를 사용하여 표시한 텍스트 윤곽선](./media/how-to-create-outlined-text/text-outline-linear-gradient.jpg)  
  
 <span data-ttu-id="816ae-110">텍스트가 <xref:System.Windows.Media.Geometry> 개체로 변환되면 더 이상 문자 컬렉션이 아니므로 텍스트 문자열의 문자를 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="816ae-110">When text is converted to a <xref:System.Windows.Media.Geometry> object, it is no longer a collection of characters—you cannot modify the characters in the text string.</span></span> <span data-ttu-id="816ae-111">그러나 스트로크와 채우기 속성을 수정하여 변환된 텍스트의 모양에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="816ae-111">However, you can affect the appearance of the converted text by modifying its stroke and fill properties.</span></span> <span data-ttu-id="816ae-112">스트로크는 변환된 텍스트의 윤곽선을 나타내고, 채우기는 변환된 텍스트의 윤곽선 내부에 있는 영역을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="816ae-112">The stroke refers to the outline of the converted text; the fill refers to the area inside the outline of the converted text.</span></span>  
  
 <span data-ttu-id="816ae-113">다음 예제에서는 변환된 텍스트의 스트로크 및 채우기를 수정하여 시각적 효과를 만드는 몇 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="816ae-113">The following examples illustrate several ways of creating visual effects by modifying the stroke and fill of converted text.</span></span>  
  
 ![채우기와 스트로크에 다른 색을 사용하는 텍스트](./media/how-to-create-outlined-text/fill-stroke-text-effect.jpg)  
  
 ![스트로크에 이미지 브러시가 적용된 텍스트](./media/how-to-create-outlined-text/image-brush-application.jpg)
  
 <span data-ttu-id="816ae-116">변환된 텍스트의 경계 상자 사각형 또는 강조 표시를 수정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="816ae-116">It is also possible to modify the bounding box rectangle, or highlight, of the converted text.</span></span> <span data-ttu-id="816ae-117">다음 예제에서는 변환된 텍스트의 스트로크및 강조 표시를 수정하여 시각적 효과를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="816ae-117">The following example illustrates a way to creating visual effects by modifying the stroke and highlight of converted text.</span></span>  
  
 ![선및 강조 표시에 이미지 브러시가 적용된 텍스트](./media/how-to-create-outlined-text/image-brush-text-application.jpg)

## <a name="example"></a><span data-ttu-id="816ae-119">예제</span><span class="sxs-lookup"><span data-stu-id="816ae-119">Example</span></span>  
 <span data-ttu-id="816ae-120">텍스트를 <xref:System.Windows.Media.Geometry> 개체로 변환하는 핵심은 개체를 <xref:System.Windows.Media.FormattedText> 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="816ae-120">The key to converting text to a <xref:System.Windows.Media.Geometry> object is to use the <xref:System.Windows.Media.FormattedText> object.</span></span> <span data-ttu-id="816ae-121">이 개체를 만든 후에는 <xref:System.Windows.Media.FormattedText.BuildGeometry%2A> 및 <xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A> 메서드를 사용하여 텍스트를 <xref:System.Windows.Media.Geometry> 개체로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="816ae-121">Once you have created this object, you can use the <xref:System.Windows.Media.FormattedText.BuildGeometry%2A> and <xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A> methods to convert the text to <xref:System.Windows.Media.Geometry> objects.</span></span> <span data-ttu-id="816ae-122">첫 번째 메서드는 서식이 지정된 텍스트의 형상을 반환합니다. 두 번째 메서드는 서식이 지정된 텍스트의 경계 상자의 형상을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="816ae-122">The first method returns the geometry of the formatted text; the second method returns the geometry of the formatted text's bounding box.</span></span> <span data-ttu-id="816ae-123">다음 코드 예제에서는 <xref:System.Windows.Media.FormattedText> 개체를 만들고 서식이 지정된 텍스트와 해당 경계 상자의 형상을 검색하는 방법을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="816ae-123">The following code example shows how to create a <xref:System.Windows.Media.FormattedText> object and to retrieve the geometries of the formatted text and its bounding box.</span></span>  
  
 [!code-csharp[OutlineTextControlViewer#CreateText](~/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#createtext)]
 [!code-vb[OutlineTextControlViewer#CreateText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#createtext)]  
  
 <span data-ttu-id="816ae-124">검색된 <xref:System.Windows.Media.Geometry> 개체를 표시하려면 변환된 텍스트를 표시하는 <xref:System.Windows.Media.DrawingContext> 개체에 액세스해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="816ae-124">In order to display the retrieved the <xref:System.Windows.Media.Geometry> objects, you need to access the <xref:System.Windows.Media.DrawingContext> of the object that is displaying the converted text.</span></span> <span data-ttu-id="816ae-125">이러한 코드 예제에서는 사용자 정의 렌더링을 지원하는 클래스에서 파생된 사용자 지정 컨트롤 개체를 만들어 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="816ae-125">In these code examples, this is done by creating a custom control object that is derived from a class that supports user-defined rendering.</span></span>  
  
 <span data-ttu-id="816ae-126">사용자 <xref:System.Windows.Media.Geometry> 지정 컨트롤에 개체를 표시하려면 메서드에 대한 재정의를 <xref:System.Windows.UIElement.OnRender%2A> 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="816ae-126">To display <xref:System.Windows.Media.Geometry> objects in the custom control, provide an override for the <xref:System.Windows.UIElement.OnRender%2A> method.</span></span> <span data-ttu-id="816ae-127">재정의 된 메서드는 <xref:System.Windows.Media.DrawingContext.DrawGeometry%2A> 메서드를 사용하여 <xref:System.Windows.Media.Geometry> 개체를 그려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="816ae-127">Your overridden method should use the <xref:System.Windows.Media.DrawingContext.DrawGeometry%2A> method to draw the <xref:System.Windows.Media.Geometry> objects.</span></span>  
  
 [!code-csharp[OutlineTextControlViewer#OnRender](~/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#onrender)]
 [!code-vb[OutlineTextControlViewer#OnRender](~/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#onrender)]  
  
  <span data-ttu-id="816ae-128">예제 사용자 제어 개체의 소스는 [C#](https://github.com/dotnet/samples/blob/master/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs) 및 [Visual Basic에 대한 개요TextControl.vb에 대한](https://github.com/dotnet/samples/blob/master/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb)OutlineTextControl.cs 를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="816ae-128">For the source of the example custom user control object, see [OutlineTextControl.cs for C#](https://github.com/dotnet/samples/blob/master/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs) and [OutlineTextControl.vb for Visual Basic](https://github.com/dotnet/samples/blob/master/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="816ae-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="816ae-129">See also</span></span>

- [<span data-ttu-id="816ae-130">서식 있는 텍스트 그리기</span><span class="sxs-lookup"><span data-stu-id="816ae-130">Drawing Formatted Text</span></span>](drawing-formatted-text.md)
