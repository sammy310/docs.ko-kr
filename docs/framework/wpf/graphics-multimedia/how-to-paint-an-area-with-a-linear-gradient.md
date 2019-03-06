---
title: '방법: 선형 그라데이션으로 영역 그리기'
ms.date: 03/30/2017
helpviewer_keywords:
- linear gradients [WPF], painting with
- brushes [WPF], painting with linear gradients
- painting [WPF], with linear gradients
ms.assetid: 00e0cd04-48c0-4ec5-850e-d321beb37a34
ms.openlocfilehash: c48ff13811d784ecc7042b73b964a9e6f2d42a34
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57367247"
---
# <a name="how-to-paint-an-area-with-a-linear-gradient"></a><span data-ttu-id="96285-102">방법: 선형 그라데이션으로 영역 그리기</span><span class="sxs-lookup"><span data-stu-id="96285-102">How to: Paint an Area with a Linear Gradient</span></span>
<span data-ttu-id="96285-103">사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.LinearGradientBrush> 선형 그라데이션으로 영역 그리기 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="96285-103">This example shows how to use the <xref:System.Windows.Media.LinearGradientBrush> class to paint an area with a linear gradient.</span></span> <span data-ttu-id="96285-104">다음 예제에서는 <xref:System.Windows.Shapes.Shape.Fill%2A> 의 <xref:System.Windows.Shapes.Rectangle> 노란색에서 빨간색에서 파란색 라임 녹색으로 전환 하는 대각선 선형 그라데이션을 사용 하 여 그려집니다.</span><span class="sxs-lookup"><span data-stu-id="96285-104">In the following example, the <xref:System.Windows.Shapes.Shape.Fill%2A> of a <xref:System.Windows.Shapes.Rectangle> is painted with a diagonal linear gradient that transitions from yellow to red to blue to lime green.</span></span>  
  
## <a name="example"></a><span data-ttu-id="96285-105">예제</span><span class="sxs-lookup"><span data-stu-id="96285-105">Example</span></span>  
 [!code-xaml[GradientBrushExamples_snip#DiagonalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#diagonalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#DiagonalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#diagonalgradient1csharp)]  
  
 <span data-ttu-id="96285-106">다음 그림에서는 이전 예제에서 만든 그라데이션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="96285-106">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="96285-107">![대각선 선형 그라데이션](./media/graphicsmm-diagonallgb.jpg "graphicsmm_DiagonalLGB")</span><span class="sxs-lookup"><span data-stu-id="96285-107">![Diagonal linear gradient](./media/graphicsmm-diagonallgb.jpg "graphicsmm_DiagonalLGB")</span></span>  
  
 <span data-ttu-id="96285-108">가로 선형 그라데이션 만들기, 변경 된 <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> 및 <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> 의 <xref:System.Windows.Media.LinearGradientBrush> (0, 0.5)에 (1, 0.5) 및 합니다.</span><span class="sxs-lookup"><span data-stu-id="96285-108">To create a horizontal linear gradient, change the <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> and <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> of the <xref:System.Windows.Media.LinearGradientBrush> to (0,0.5) and (1,0.5).</span></span> <span data-ttu-id="96285-109">다음 예제에서는 <xref:System.Windows.Shapes.Rectangle> 가로 선형 그라데이션을 사용 하 여 그려집니다.</span><span class="sxs-lookup"><span data-stu-id="96285-109">In the following example, a <xref:System.Windows.Shapes.Rectangle> is painted with a horizontal linear gradient.</span></span>  
  
 [!code-xaml[GradientBrushExamples_snip#HorizontalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#horizontalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#HorizontalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#horizontalgradient1csharp)]  
  
 <span data-ttu-id="96285-110">다음 그림에서는 이전 예제에서 만든 그라데이션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="96285-110">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="96285-111">![가로 선형 그라데이션의](./media/graphicsmm-horizontallgb.jpg "graphicsmm_HorizontalLGB")</span><span class="sxs-lookup"><span data-stu-id="96285-111">![A horizontal linear gradient](./media/graphicsmm-horizontallgb.jpg "graphicsmm_HorizontalLGB")</span></span>  
  
 <span data-ttu-id="96285-112">세로 선형 그라데이션 만들기, 변경 된 <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> 및 <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> 의 <xref:System.Windows.Media.LinearGradientBrush> (0.5, 0)을 (0.5, 1) 및 합니다.</span><span class="sxs-lookup"><span data-stu-id="96285-112">To create a vertical linear gradient, change the <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> and <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> of the <xref:System.Windows.Media.LinearGradientBrush> to (0.5,0) and (0.5,1).</span></span> <span data-ttu-id="96285-113">다음 예제에서는 <xref:System.Windows.Shapes.Rectangle> 세로 선형 그라데이션을 사용 하 여 그려집니다.</span><span class="sxs-lookup"><span data-stu-id="96285-113">In the following example, a <xref:System.Windows.Shapes.Rectangle> is painted with a vertical linear gradient.</span></span>  
  
 [!code-xaml[GradientBrushExamples_snip#VerticalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#verticalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#VerticalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#verticalgradient1csharp)]  
  
 <span data-ttu-id="96285-114">다음 그림에서는 이전 예제에서 만든 그라데이션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="96285-114">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="96285-115">![세로 선형 그라데이션](./media/graphicsmm-verticallgb.jpg "graphicsmm_VerticalLGB")</span><span class="sxs-lookup"><span data-stu-id="96285-115">![Vertical linear gradient](./media/graphicsmm-verticallgb.jpg "graphicsmm_VerticalLGB")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="96285-116">이 항목의 예제는 시작점 및 끝점 설정에 대 한 기본 좌표계를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="96285-116">The examples in this topic use the default coordinate system for setting start points and end points.</span></span> <span data-ttu-id="96285-117">기본 좌표계는 경계 상자를 기준으로 합니다. 0은 경계 상자의 0%를 나타내고 1은 경계 상자의 100%를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="96285-117">The default coordinate system is relative to a bounding box: 0 indicates 0 percent of the bounding box, and 1 indicates 100 percent of the bounding box.</span></span> <span data-ttu-id="96285-118">설정 하 여이 좌표계를 변경할 수 있습니다 합니다 <xref:System.Windows.Media.GradientBrush.MappingMode%2A> 속성 값을 <xref:System.Windows.Media.BrushMappingMode.Absolute?displayProperty=nameWithType>입니다.</span><span class="sxs-lookup"><span data-stu-id="96285-118">You can change this coordinate system by setting the <xref:System.Windows.Media.GradientBrush.MappingMode%2A> property to the value <xref:System.Windows.Media.BrushMappingMode.Absolute?displayProperty=nameWithType>.</span></span> <span data-ttu-id="96285-119">절대 좌표계는 경계 상자를 기준으로 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96285-119">An absolute coordinate system is not relative to a bounding box.</span></span> <span data-ttu-id="96285-120">값은 로컬 공간에서 직접 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="96285-120">Values are interpreted directly in local space.</span></span>  
  
 <span data-ttu-id="96285-121">추가 예제를 보려면 [브러시 샘플](https://go.microsoft.com/fwlink/?LinkID=159973)합니다.</span><span class="sxs-lookup"><span data-stu-id="96285-121">For additional examples, see [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span></span> <span data-ttu-id="96285-122">그라데이션 및 브러시의 다른 형식에 대 한 자세한 내용은 참조 하세요. [단색 및 그라데이션 개요 그리기](painting-with-solid-colors-and-gradients-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="96285-122">For more information about gradients and other types of brushes, see [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>
