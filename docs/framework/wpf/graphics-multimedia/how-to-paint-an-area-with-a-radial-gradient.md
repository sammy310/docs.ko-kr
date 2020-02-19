---
title: '방법: 방사형 그라데이션으로 영역 그리기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], painting with radial gradients
- radial gradients [WPF], painting with
- painting [WPF], with radial gradients
ms.assetid: b5d0fc8a-8986-4796-b003-a75b41a48928
ms.openlocfilehash: 8a53d5d7247f82905816265f7c92b22f287591c5
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452755"
---
# <a name="how-to-paint-an-area-with-a-radial-gradient"></a><span data-ttu-id="64b0c-102">방법: 방사형 그라데이션으로 영역 그리기</span><span class="sxs-lookup"><span data-stu-id="64b0c-102">How to: Paint an Area with a Radial Gradient</span></span>
<span data-ttu-id="64b0c-103">이 예제에서는 <xref:System.Windows.Media.RadialGradientBrush> 클래스를 사용 하 여 방사형 그라데이션으로 영역을 그리는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="64b0c-103">This example shows how to use the <xref:System.Windows.Media.RadialGradientBrush> class to paint an area with a radial gradient.</span></span>  
  
## <a name="example"></a><span data-ttu-id="64b0c-104">예제</span><span class="sxs-lookup"><span data-stu-id="64b0c-104">Example</span></span>  
 <span data-ttu-id="64b0c-105">다음 예에서는 <xref:System.Windows.Media.RadialGradientBrush>를 사용 하 여 노랑에서 빨강, 파랑, 녹색으로 전환 되는 방사형 그라데이션으로 사각형을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="64b0c-105">The following example uses a <xref:System.Windows.Media.RadialGradientBrush> to paint a rectangle with a radial gradient that transitions from yellow to red to blue to lime green.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/RadialGradientBrushSnippet.cs#simpleradialgradientexamplewholepage)]
 [!code-vb[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/radialgradientbrushsnippet.vb#simpleradialgradientexamplewholepage)]
 [!code-xaml[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/RadialGradientBrushSnippet.xaml#simpleradialgradientexamplewholepage)]  
  
 <span data-ttu-id="64b0c-106">다음 그림에서는 이전 예제의 그라데이션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="64b0c-106">The following illustration shows the gradient from the preceding example.</span></span> <span data-ttu-id="64b0c-107">그라데이션 중지점이 강조 표시 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="64b0c-107">The gradient's stops have been highlighted.</span></span>  
  
 <span data-ttu-id="64b0c-108">![방사형 그라데이션의 그라데이션 중지점](./media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops_rg")</span><span class="sxs-lookup"><span data-stu-id="64b0c-108">![Gradient stops in a radial gradient](./media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops_rg")</span></span>  
  
> [!NOTE]
> <span data-ttu-id="64b0c-109">이 항목의 예제에서는 기본 좌표계를 사용 하 여 컨트롤 요소를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="64b0c-109">The examples in this topic use the default coordinate system for setting control points.</span></span> <span data-ttu-id="64b0c-110">기본 좌표계는 경계 상자를 기준으로 합니다. 0은 경계 상자의 0%를 나타내고 1은 경계 상자의 100%를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="64b0c-110">The default coordinate system is relative to a bounding box: 0 indicates 0 percent of the bounding box, and 1 indicates 100 percent of the bounding box.</span></span> <span data-ttu-id="64b0c-111"><xref:System.Windows.Media.GradientBrush.MappingMode%2A> 속성을 <xref:System.Windows.Media.BrushMappingMode.Absolute>값으로 설정 하 여이 좌표계를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64b0c-111">You can change this coordinate system by setting the <xref:System.Windows.Media.GradientBrush.MappingMode%2A> property to the value <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span></span> <span data-ttu-id="64b0c-112">절대 좌표계는 경계 상자를 기준으로 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="64b0c-112">An absolute coordinate system is not relative to a bounding box.</span></span> <span data-ttu-id="64b0c-113">값은 로컬 공간에서 직접 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="64b0c-113">Values are interpreted directly in local space.</span></span>  
  
 <span data-ttu-id="64b0c-114">추가 <xref:System.Windows.Media.RadialGradientBrush> 예제는 [브러시 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="64b0c-114">For additional <xref:System.Windows.Media.RadialGradientBrush> examples, see the [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span></span> <span data-ttu-id="64b0c-115">그라데이션 및 기타 브러시 형식에 대 한 자세한 내용은 [단색 및 그라데이션을 사용한 그리기 개요](painting-with-solid-colors-and-gradients-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="64b0c-115">For more information about gradients and other types of brushes, see [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>
