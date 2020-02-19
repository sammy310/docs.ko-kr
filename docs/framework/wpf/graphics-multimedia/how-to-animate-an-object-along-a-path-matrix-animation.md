---
title: '방법: 경로를 따라 개체에 애니메이션 효과 주기(매트릭스 애니메이션)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (matrix animation)
- matrix animation [WPF]
ms.assetid: 7000e697-1414-468c-b915-cf66062fc49e
ms.openlocfilehash: 7dfc233fe60e1cea293edc44a2bba79dc6962f7c
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452911"
---
# <a name="how-to-animate-an-object-along-a-path-matrix-animation"></a><span data-ttu-id="bc30b-102">방법: 경로를 따라 개체에 애니메이션 효과 주기(매트릭스 애니메이션)</span><span class="sxs-lookup"><span data-stu-id="bc30b-102">How to: Animate an Object Along a Path (Matrix Animation)</span></span>
<span data-ttu-id="bc30b-103">이 예제에서는 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 클래스를 사용 하 여 <xref:System.Windows.Media.PathGeometry>에서 정의한 경로를 따라 개체에 애니메이션 효과를 주는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bc30b-103">This example shows how to use the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> class to animate an object along a path that is defined by a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc30b-104">예제</span><span class="sxs-lookup"><span data-stu-id="bc30b-104">Example</span></span>  
 <span data-ttu-id="bc30b-105">다음 예제에서는 다음을 수행하여 경로를 따라 개체에 애니메이션 효과를 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bc30b-105">The following example animates an object along a path by doing the following:</span></span>  
  
- <span data-ttu-id="bc30b-106">개체를 이동 하기 위해 개체에 <xref:System.Windows.Media.MatrixTransform>을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc30b-106">Applies a <xref:System.Windows.Media.MatrixTransform> to the object in order to move it.</span></span>  
  
- <span data-ttu-id="bc30b-107"><xref:System.Windows.Media.PathGeometry>를 사용 하 여 경로를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc30b-107">Defines the path by using a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
- <span data-ttu-id="bc30b-108"><xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>를 만들고이를 사용 하 여 <xref:System.Windows.Media.MatrixTransform>의 <xref:System.Windows.Media.Matrix> 속성에 애니메이션 효과를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc30b-108">Creates a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> and uses it to animate the <xref:System.Windows.Media.Matrix> property of the <xref:System.Windows.Media.MatrixTransform>.</span></span> <span data-ttu-id="bc30b-109"><xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> <xref:System.Windows.Media.PathGeometry>를 사용 하 고이를 사용 하 여 <xref:System.Windows.Media.Matrix> 값을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc30b-109">The <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> takes the <xref:System.Windows.Media.PathGeometry> and uses it to generate <xref:System.Windows.Media.Matrix> values.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathexample.xaml#matrixanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathExample.cs#matrixanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathExample.vb#matrixanimationusingpathwholepage)]  
  
 <span data-ttu-id="bc30b-110">전체 샘플은 [경로 애니메이션 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bc30b-110">For the complete sample, see [Path Animation Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).</span></span> <span data-ttu-id="bc30b-111">기하학적 경로에 대 한 자세한 내용은 [Geometry 개요](geometry-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bc30b-111">For more information about geometric paths, see the [Geometry Overview](geometry-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc30b-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bc30b-112">See also</span></span>

- [<span data-ttu-id="bc30b-113">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="bc30b-113">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="bc30b-114">경로 애니메이션 샘플</span><span class="sxs-lookup"><span data-stu-id="bc30b-114">Path Animation Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
- [<span data-ttu-id="bc30b-115">경로 애니메이션 방법 항목</span><span class="sxs-lookup"><span data-stu-id="bc30b-115">Path Animation How-to Topics</span></span>](path-animation-how-to-topics.md)
