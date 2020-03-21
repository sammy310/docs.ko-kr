---
title: '방법: 기하학적 경로를 사용하여 개체 회전(매트릭스 애니메이션)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- geometric paths [WPF], rotating objects by
- rotating objects by geometric paths [WPF]
- matrix animation [WPF]
ms.assetid: 877dc9aa-6bdc-4beb-8772-3efaec32c0f0
ms.openlocfilehash: 63dc873a2b840ea3f870a8c60c5691ab271c1c9f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187417"
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation"></a><span data-ttu-id="c4176-102">방법: 기하학적 경로를 사용하여 개체 회전(매트릭스 애니메이션)</span><span class="sxs-lookup"><span data-stu-id="c4176-102">How to: Rotate an Object by Using a Geometric Path (Matrix Animation)</span></span>
<span data-ttu-id="c4176-103">이 예제에서는 객체에 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 의해 <xref:System.Windows.Media.MatrixTransform> 정의된 기하학적 경로를 따라 a와 a를 사용하여 오브젝트를 회전(피벗)하는 방법을 보여 주며, 이 예제에서는 객체를 회전(피봇)하는 <xref:System.Windows.Media.PathGeometry> 방법을 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="c4176-103">This example shows how to use a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> and a <xref:System.Windows.Media.MatrixTransform> to rotate (pivot) an object along a geometric path defined by a <xref:System.Windows.Media.PathGeometry> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c4176-104">예제</span><span class="sxs-lookup"><span data-stu-id="c4176-104">Example</span></span>  
 <span data-ttu-id="c4176-105">다음 예제에서는 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 개체를 사용하여 의 <xref:System.Windows.Media.MatrixTransform.Matrix%2A> 속성을 <xref:System.Windows.Media.MatrixTransform>애니메이션합니다.</span><span class="sxs-lookup"><span data-stu-id="c4176-105">The following example uses the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform>.</span></span> <span data-ttu-id="c4176-106">는 <xref:System.Windows.Media.MatrixTransform> 단추에 적용되고 곡선 된 경로를 따라 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c4176-106">The <xref:System.Windows.Media.MatrixTransform> is applied to a button and causes it to move along a curved path.</span></span> <span data-ttu-id="c4176-107">속성이 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> 설정되므로 `true`사각형이 패스의 접선을 따라 회전합니다.</span><span class="sxs-lookup"><span data-stu-id="c4176-107">Because the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> property is set to `true`, the rectangle rotates along the tangent of the path.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathdoesrotatewithtangentexample.xaml#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathDoesRotateWithTangentExample.cs#matrixanimationusingpathdoesrotatewithtangentwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathDoesRotateWithTangentExample.vb#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 <span data-ttu-id="c4176-108">전체 샘플은 [경로 애니메이션 샘플을](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c4176-108">For the complete sample, see [Path Animation Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).</span></span>  
  
 <span data-ttu-id="c4176-109">이전 샘플의 코드 버전은 하나의 <xref:System.Windows.Media.Animation.Storyboard> 애니메이션만 적용되었음에도 불구하고 에 애니메이션을 <xref:System.Windows.Media.EllipseGeometry>적용하는 데 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="c4176-109">The code version of the preceding sample used a <xref:System.Windows.Media.Animation.Storyboard> to animate the <xref:System.Windows.Media.EllipseGeometry>, even though only one animation was applied.</span></span> <span data-ttu-id="c4176-110">코드의 속성에 단일 애니메이션을 적용하는 더 쉬운 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 방법은 메서드를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c4176-110">An easier way to apply a single animation to a property in code is to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method.</span></span> <span data-ttu-id="c4176-111">예를 들어 [스토리보드를 사용하지 않고 속성 애니메이션을](how-to-animate-a-property-without-using-a-storyboard.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c4176-111">For an example, see [Animate a Property Without Using a Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4176-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c4176-112">See also</span></span>

- [<span data-ttu-id="c4176-113">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="c4176-113">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="c4176-114">경로 애니메이션 방법 항목</span><span class="sxs-lookup"><span data-stu-id="c4176-114">Path Animation How-to Topics</span></span>](path-animation-how-to-topics.md)
- [<span data-ttu-id="c4176-115">경로 애니메이션 샘플</span><span class="sxs-lookup"><span data-stu-id="c4176-115">Path Animation Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
