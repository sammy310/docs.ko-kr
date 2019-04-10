---
title: '방법: 경로를 따라 개체에 애니메이션 효과 주기(Matrix 애니메이션)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (matrix animation)
- matrix animation [WPF]
ms.assetid: 7000e697-1414-468c-b915-cf66062fc49e
ms.openlocfilehash: ab15126680b7d8c6936246a7dae2f67c7541233b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59190927"
---
# <a name="how-to-animate-an-object-along-a-path-matrix-animation"></a><span data-ttu-id="1f889-102">방법: 경로를 따라 개체에 애니메이션 효과 주기(Matrix 애니메이션)</span><span class="sxs-lookup"><span data-stu-id="1f889-102">How to: Animate an Object Along a Path (Matrix Animation)</span></span>
<span data-ttu-id="1f889-103">사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 클래스에서 정의 된 경로 따라 개체에 애니메이션 효과를 <xref:System.Windows.Media.PathGeometry>합니다.</span><span class="sxs-lookup"><span data-stu-id="1f889-103">This example shows how to use the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> class to animate an object along a path that is defined by a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f889-104">예제</span><span class="sxs-lookup"><span data-stu-id="1f889-104">Example</span></span>  
 <span data-ttu-id="1f889-105">다음 예제에서는 다음을 수행하여 경로를 따라 개체에 애니메이션 효과를 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1f889-105">The following example animates an object along a path by doing the following:</span></span>  
  
-   <span data-ttu-id="1f889-106">적용 되는 <xref:System.Windows.Media.MatrixTransform> 이동 하기 위해 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="1f889-106">Applies a <xref:System.Windows.Media.MatrixTransform> to the object in order to move it.</span></span>  
  
-   <span data-ttu-id="1f889-107">경로 사용 하 여 정의 된 <xref:System.Windows.Media.PathGeometry>합니다.</span><span class="sxs-lookup"><span data-stu-id="1f889-107">Defines the path by using a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
-   <span data-ttu-id="1f889-108">만듭니다는 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 애니메이션을 적용 하는 데 사용 합니다 <xref:System.Windows.Media.Matrix> 의 속성을 <xref:System.Windows.Media.MatrixTransform>.</span><span class="sxs-lookup"><span data-stu-id="1f889-108">Creates a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> and uses it to animate the <xref:System.Windows.Media.Matrix> property of the <xref:System.Windows.Media.MatrixTransform>.</span></span> <span data-ttu-id="1f889-109"><xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 사용 합니다 <xref:System.Windows.Media.PathGeometry> 생성 하는 데 사용 하 고 <xref:System.Windows.Media.Matrix> 값.</span><span class="sxs-lookup"><span data-stu-id="1f889-109">The <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> takes the <xref:System.Windows.Media.PathGeometry> and uses it to generate <xref:System.Windows.Media.Matrix> values.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathexample.xaml#matrixanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathExample.cs#matrixanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathExample.vb#matrixanimationusingpathwholepage)]  
  
 <span data-ttu-id="1f889-110">전체 샘플을 참조 하세요 [경로 애니메이션 샘플](https://go.microsoft.com/fwlink/?LinkID=160028)합니다.</span><span class="sxs-lookup"><span data-stu-id="1f889-110">For the complete sample, see [Path Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160028).</span></span> <span data-ttu-id="1f889-111">기하학적 경로 대 한 자세한 내용은 참조는 [기 하 도형 개요](geometry-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1f889-111">For more information about geometric paths, see the [Geometry Overview](geometry-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f889-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="1f889-112">See also</span></span>

- [<span data-ttu-id="1f889-113">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="1f889-113">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="1f889-114">경로 애니메이션 샘플</span><span class="sxs-lookup"><span data-stu-id="1f889-114">Path Animation Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160028)
- [<span data-ttu-id="1f889-115">경로 애니메이션 방법 항목</span><span class="sxs-lookup"><span data-stu-id="1f889-115">Path Animation How-to Topics</span></span>](path-animation-how-to-topics.md)
