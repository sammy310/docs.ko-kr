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
ms.openlocfilehash: c3bcc11dea4b1f223f629415591ab03588881dde
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57379785"
---
# <a name="how-to-paint-an-area-with-a-radial-gradient"></a><span data-ttu-id="e2411-102">방법: 방사형 그라데이션으로 영역 그리기</span><span class="sxs-lookup"><span data-stu-id="e2411-102">How to: Paint an Area with a Radial Gradient</span></span>
<span data-ttu-id="e2411-103">사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.RadialGradientBrush> 방사형 그라데이션으로 영역 그리기 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="e2411-103">This example shows how to use the <xref:System.Windows.Media.RadialGradientBrush> class to paint an area with a radial gradient.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2411-104">예제</span><span class="sxs-lookup"><span data-stu-id="e2411-104">Example</span></span>  
 <span data-ttu-id="e2411-105">다음 예제에서는 <xref:System.Windows.Media.RadialGradientBrush> 노란색에서 빨간색에서 파란색 라임 녹색으로 전환 하는 방사형 그라데이션 사용 하 여 사각형을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="e2411-105">The following example uses a <xref:System.Windows.Media.RadialGradientBrush> to paint a rectangle with a radial gradient that transitions from yellow to red to blue to lime green.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/RadialGradientBrushSnippet.cs#simpleradialgradientexamplewholepage)]
 [!code-vb[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/radialgradientbrushsnippet.vb#simpleradialgradientexamplewholepage)]
 [!code-xaml[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/RadialGradientBrushSnippet.xaml#simpleradialgradientexamplewholepage)]  
  
 <span data-ttu-id="e2411-106">다음 그림에서는 앞의 예제에서 그라데이션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e2411-106">The following illustration shows the gradient from the preceding example.</span></span> <span data-ttu-id="e2411-107">그라데이션 중지점의 중지를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2411-107">The gradient's stops have been highlighted.</span></span>  
  
 <span data-ttu-id="e2411-108">![방사형 그라데이션의 그라데이션 중지점](./media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops")</span><span class="sxs-lookup"><span data-stu-id="e2411-108">![Gradient stops in a radial gradient](./media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops_rg")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e2411-109">제어점을 설정 하기 위한 기본 좌표계를 사용 하는이 항목의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="e2411-109">The examples in this topic use the default coordinate system for setting control points.</span></span> <span data-ttu-id="e2411-110">기본 좌표계는 경계 상자를 기준으로 합니다. 0은 경계 상자의 0%를 나타내고 1은 경계 상자의 100%를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e2411-110">The default coordinate system is relative to a bounding box: 0 indicates 0 percent of the bounding box, and 1 indicates 100 percent of the bounding box.</span></span> <span data-ttu-id="e2411-111">설정 하 여이 좌표계를 변경할 수 있습니다 합니다 <xref:System.Windows.Media.GradientBrush.MappingMode%2A> 속성 값을 <xref:System.Windows.Media.BrushMappingMode.Absolute>입니다.</span><span class="sxs-lookup"><span data-stu-id="e2411-111">You can change this coordinate system by setting the <xref:System.Windows.Media.GradientBrush.MappingMode%2A> property to the value <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span></span> <span data-ttu-id="e2411-112">절대 좌표계는 경계 상자를 기준으로 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e2411-112">An absolute coordinate system is not relative to a bounding box.</span></span> <span data-ttu-id="e2411-113">값은 로컬 공간에서 직접 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2411-113">Values are interpreted directly in local space.</span></span>  
  
 <span data-ttu-id="e2411-114">에 대 한 추가 <xref:System.Windows.Media.RadialGradientBrush> 예제를 참조 합니다 [브러시 샘플](https://go.microsoft.com/fwlink/?LinkID=159973)합니다.</span><span class="sxs-lookup"><span data-stu-id="e2411-114">For additional <xref:System.Windows.Media.RadialGradientBrush> examples, see the [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span></span> <span data-ttu-id="e2411-115">그라데이션 및 브러시의 다른 형식에 대 한 자세한 내용은 참조 하세요. [단색 및 그라데이션 개요 그리기](painting-with-solid-colors-and-gradients-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e2411-115">For more information about gradients and other types of brushes, see [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>
