---
title: '방법: 선형 그라데이션으로 영역 그리기'
ms.date: 03/30/2017
helpviewer_keywords:
- linear gradients [WPF], painting with
- brushes [WPF], painting with linear gradients
- painting [WPF], with linear gradients
ms.assetid: 00e0cd04-48c0-4ec5-850e-d321beb37a34
ms.openlocfilehash: 76c491632911c48db34d932ba3895278591378a5
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452768"
---
# <a name="how-to-paint-an-area-with-a-linear-gradient"></a><span data-ttu-id="1939e-102">방법: 선형 그라데이션으로 영역 그리기</span><span class="sxs-lookup"><span data-stu-id="1939e-102">How to: Paint an Area with a Linear Gradient</span></span>
<span data-ttu-id="1939e-103">이 예제에서는 <xref:System.Windows.Media.LinearGradientBrush> 클래스를 사용 하 여 선형 그라데이션으로 영역을 그리는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1939e-103">This example shows how to use the <xref:System.Windows.Media.LinearGradientBrush> class to paint an area with a linear gradient.</span></span> <span data-ttu-id="1939e-104">다음 예제에서는 <xref:System.Windows.Shapes.Rectangle>의 <xref:System.Windows.Shapes.Shape.Fill%2A> 노랑에서 빨강, 파랑, 녹색으로 전환 되는 대각선 선형 그라데이션으로 그려집니다.</span><span class="sxs-lookup"><span data-stu-id="1939e-104">In the following example, the <xref:System.Windows.Shapes.Shape.Fill%2A> of a <xref:System.Windows.Shapes.Rectangle> is painted with a diagonal linear gradient that transitions from yellow to red to blue to lime green.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1939e-105">예제</span><span class="sxs-lookup"><span data-stu-id="1939e-105">Example</span></span>  
 [!code-xaml[GradientBrushExamples_snip#DiagonalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#diagonalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#DiagonalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#diagonalgradient1csharp)]  
  
 <span data-ttu-id="1939e-106">다음 그림은 이전 예제에서 만든 그라데이션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1939e-106">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="1939e-107">![대각선 선형 그라데이션](./media/graphicsmm-diagonallgb.jpg "graphicsmm_DiagonalLGB")</span><span class="sxs-lookup"><span data-stu-id="1939e-107">![Diagonal linear gradient](./media/graphicsmm-diagonallgb.jpg "graphicsmm_DiagonalLGB")</span></span>  
  
 <span data-ttu-id="1939e-108">가로 선형 그라데이션을 만들려면 <xref:System.Windows.Media.LinearGradientBrush>의 <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> 및 <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> (0, 0.5) 및 (1, 0.5)로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="1939e-108">To create a horizontal linear gradient, change the <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> and <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> of the <xref:System.Windows.Media.LinearGradientBrush> to (0,0.5) and (1,0.5).</span></span> <span data-ttu-id="1939e-109">다음 예에서는 가로 선형 그라데이션으로 <xref:System.Windows.Shapes.Rectangle>를 그립니다.</span><span class="sxs-lookup"><span data-stu-id="1939e-109">In the following example, a <xref:System.Windows.Shapes.Rectangle> is painted with a horizontal linear gradient.</span></span>  
  
 [!code-xaml[GradientBrushExamples_snip#HorizontalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#horizontalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#HorizontalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#horizontalgradient1csharp)]  
  
 <span data-ttu-id="1939e-110">다음 그림은 이전 예제에서 만든 그라데이션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1939e-110">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="1939e-111">![가로 선형 그라데이션](./media/graphicsmm-horizontallgb.jpg "graphicsmm_HorizontalLGB")</span><span class="sxs-lookup"><span data-stu-id="1939e-111">![A horizontal linear gradient](./media/graphicsmm-horizontallgb.jpg "graphicsmm_HorizontalLGB")</span></span>  
  
 <span data-ttu-id="1939e-112">세로 선형 그라데이션을 만들려면 <xref:System.Windows.Media.LinearGradientBrush>의 <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> 및 <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> (0.5, 0) 및 (0.5, 1)로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="1939e-112">To create a vertical linear gradient, change the <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> and <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> of the <xref:System.Windows.Media.LinearGradientBrush> to (0.5,0) and (0.5,1).</span></span> <span data-ttu-id="1939e-113">다음 예에서는 <xref:System.Windows.Shapes.Rectangle> 세로 선형 그라데이션으로 그려집니다.</span><span class="sxs-lookup"><span data-stu-id="1939e-113">In the following example, a <xref:System.Windows.Shapes.Rectangle> is painted with a vertical linear gradient.</span></span>  
  
 [!code-xaml[GradientBrushExamples_snip#VerticalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#verticalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#VerticalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#verticalgradient1csharp)]  
  
 <span data-ttu-id="1939e-114">다음 그림은 이전 예제에서 만든 그라데이션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1939e-114">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="1939e-115">![세로 선형 그라데이션](./media/graphicsmm-verticallgb.jpg "graphicsmm_VerticalLGB")</span><span class="sxs-lookup"><span data-stu-id="1939e-115">![Vertical linear gradient](./media/graphicsmm-verticallgb.jpg "graphicsmm_VerticalLGB")</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1939e-116">이 항목의 예에서는 기본 좌표계를 사용 하 여 시작점 및 끝점을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1939e-116">The examples in this topic use the default coordinate system for setting start points and end points.</span></span> <span data-ttu-id="1939e-117">기본 좌표계는 경계 상자를 기준으로 합니다. 0은 경계 상자의 0%를 나타내고 1은 경계 상자의 100%를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1939e-117">The default coordinate system is relative to a bounding box: 0 indicates 0 percent of the bounding box, and 1 indicates 100 percent of the bounding box.</span></span> <span data-ttu-id="1939e-118"><xref:System.Windows.Media.GradientBrush.MappingMode%2A> 속성을 <xref:System.Windows.Media.BrushMappingMode.Absolute?displayProperty=nameWithType>값으로 설정 하 여이 좌표계를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1939e-118">You can change this coordinate system by setting the <xref:System.Windows.Media.GradientBrush.MappingMode%2A> property to the value <xref:System.Windows.Media.BrushMappingMode.Absolute?displayProperty=nameWithType>.</span></span> <span data-ttu-id="1939e-119">절대 좌표계는 경계 상자를 기준으로 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1939e-119">An absolute coordinate system is not relative to a bounding box.</span></span> <span data-ttu-id="1939e-120">값은 로컬 공간에서 직접 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="1939e-120">Values are interpreted directly in local space.</span></span>  
  
 <span data-ttu-id="1939e-121">추가 예제는 [브러시 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1939e-121">For additional examples, see [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span></span> <span data-ttu-id="1939e-122">그라데이션 및 기타 브러시 형식에 대 한 자세한 내용은 [단색 및 그라데이션을 사용한 그리기 개요](painting-with-solid-colors-and-gradients-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1939e-122">For more information about gradients and other types of brushes, see [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>
