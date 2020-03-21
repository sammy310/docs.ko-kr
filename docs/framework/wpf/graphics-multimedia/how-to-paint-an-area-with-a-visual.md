---
title: '방법: 시각적 요소로 영역 그리기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- painting [WPF]
- visuals [WPF], painting with
- brushes [WPF], painting with visuals
ms.assetid: 35f92996-1d03-4542-acc4-3469dcf09492
ms.openlocfilehash: 793a14f0d395a60bf73ca7dc173b82237a139f35
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78849369"
---
# <a name="how-to-paint-an-area-with-a-visual"></a><span data-ttu-id="aa94c-102">방법: 시각적 요소로 영역 그리기</span><span class="sxs-lookup"><span data-stu-id="aa94c-102">How to: Paint an Area with a Visual</span></span>
<span data-ttu-id="aa94c-103">이 예제에서는 클래스를 <xref:System.Windows.Media.VisualBrush> 사용하여 <xref:System.Windows.Media.Visual>영역을 로 그리는 방법을 보여 주며.</span><span class="sxs-lookup"><span data-stu-id="aa94c-103">This example shows how to use the <xref:System.Windows.Media.VisualBrush> class to paint an area with a <xref:System.Windows.Media.Visual>.</span></span>  
  
 <span data-ttu-id="aa94c-104">다음 예제에서는 여러 컨트롤과 패널이 사각형의 배경으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa94c-104">In the following example, several controls and a panel are used as the background of a rectangle.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aa94c-105">예제</span><span class="sxs-lookup"><span data-stu-id="aa94c-105">Example</span></span>  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/VisualBrushExample.xaml#graphicsmmvisualbrushasrectanglebackgroundexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/VisualBrushExample.cs#graphicsmmvisualbrushasrectanglebackgroundexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/visualbrushexample.vb#graphicsmmvisualbrushasrectanglebackgroundexample1)]  
  
 <span data-ttu-id="aa94c-106">및 추가 <xref:System.Windows.Media.VisualBrush> 예제에 대한 자세한 내용은 [이미지, 도면 및 시각적 개체가 있는 페인팅 개요를](painting-with-images-drawings-and-visuals.md) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="aa94c-106">For more information about <xref:System.Windows.Media.VisualBrush> and additional examples, see the [Painting with Images, Drawings, and Visuals](painting-with-images-drawings-and-visuals.md) overview.</span></span>  
  
 <span data-ttu-id="aa94c-107">이 코드 예제는에 대해 제공 된 큰 예제의 일부는 <xref:System.Windows.Media.VisualBrush> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="aa94c-107">This code example is part of a larger example provided for the <xref:System.Windows.Media.VisualBrush> class.</span></span> <span data-ttu-id="aa94c-108">전체 샘플은 [VisualBrush 샘플을](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/VisualBrush)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="aa94c-108">For the complete sample, see the [VisualBrush Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/VisualBrush).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa94c-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aa94c-109">See also</span></span>

- [<span data-ttu-id="aa94c-110">이미지, 그림 및 시각적 표시로 그리기</span><span class="sxs-lookup"><span data-stu-id="aa94c-110">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
