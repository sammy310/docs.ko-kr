---
title: '방법: 기하학적 경로를 사용하여 개체 회전'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- geometric paths [WPF], rotating objects by
- rotating objects by geometric paths [WPF]
ms.assetid: cb31ca4d-f05a-4c6b-9a18-4b6faaf38d45
ms.openlocfilehash: a351fdc936f634b7c57ba5a49e51501f7572a3c9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186870"
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path"></a><span data-ttu-id="f8ea0-102">방법: 기하학적 경로를 사용하여 개체 회전</span><span class="sxs-lookup"><span data-stu-id="f8ea0-102">How to: Rotate an Object by Using a Geometric Path</span></span>
<span data-ttu-id="f8ea0-103">이 예제에서는 오브젝트에 의해 정의된 기하학적 경로를 따라 오브젝트를 회전(피벗)하는 방법을 보여 주며, 이 예제에서는 오브젝트를 <xref:System.Windows.Media.PathGeometry> 회전(피벗)하는 방법을 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="f8ea0-103">This example shows how to rotate (pivot) an object along a geometric path that is defined by a <xref:System.Windows.Media.PathGeometry> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8ea0-104">예제</span><span class="sxs-lookup"><span data-stu-id="f8ea0-104">Example</span></span>  
 <span data-ttu-id="f8ea0-105">다음 예제에서는 <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> 세 개의 오브젝트를 사용하여 기하학적 경로를 따라 사각형을 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f8ea0-105">The following example uses three <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> objects to move a rectangle along a geometric path.</span></span>  
  
- <span data-ttu-id="f8ea0-106">첫 <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> 번째 애니메이션은 <xref:System.Windows.Media.RotateTransform> 사각형에 적용되는 애니메이션을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="f8ea0-106">The first <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animates a <xref:System.Windows.Media.RotateTransform> that is applied to the rectangle.</span></span> <span data-ttu-id="f8ea0-107">애니메이션은 각도 값을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f8ea0-107">The animation generates angle values.</span></span> <span data-ttu-id="f8ea0-108">이를 통해 사각형이 경로 윤곽을 따라 회전(피벗)하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8ea0-108">It makes the rectangle rotate (pivot) along the contours of the path.</span></span>  
  
- <span data-ttu-id="f8ea0-109">다른 두 개체는 <xref:System.Windows.Media.TranslateTransform.X%2A> 사각형에 <xref:System.Windows.Media.TranslateTransform.Y%2A> 적용되는 <xref:System.Windows.Media.TranslateTransform> a의 값과 애니메이션을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="f8ea0-109">The other two objects animate the <xref:System.Windows.Media.TranslateTransform.X%2A> and <xref:System.Windows.Media.TranslateTransform.Y%2A> values of a <xref:System.Windows.Media.TranslateTransform> that is applied to the rectangle.</span></span> <span data-ttu-id="f8ea0-110">이를 통해 사각형이 경로를 따라 가로 및 세로로 이동하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8ea0-110">They make the rectangle move horizontally and vertically along the path.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#RotateAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/rotateanimationusingpathexample.xaml#rotateanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/RotateAnimationUsingPathExample.cs#rotateanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/RotateAnimationUsingPathExample.vb#rotateanimationusingpathwholepage)]  
  
 <span data-ttu-id="f8ea0-111">기하학적 경로를 사용하여 오브젝트를 회전하는 또 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 다른 방법은 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> 객체를 `true`사용하고 해당 속성을 로 설정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f8ea0-111">Another way to rotate an object by using a geometric path is to use a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object and set its <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> property to `true`.</span></span> <span data-ttu-id="f8ea0-112">자세한 정보 및 예제는 [기하학적 경로(행렬 애니메이션)를 사용하여 오브젝트 회전을](how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f8ea0-112">For more information and an example, see [Rotate an Object by Using a Geometric Path (Matrix Animation)](how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation.md).</span></span>  
  
 <span data-ttu-id="f8ea0-113">전체 샘플은 [경로 애니메이션 샘플을](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f8ea0-113">For the complete sample, see [Path Animation Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8ea0-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f8ea0-114">See also</span></span>

- [<span data-ttu-id="f8ea0-115">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="f8ea0-115">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="f8ea0-116">경로 애니메이션 샘플</span><span class="sxs-lookup"><span data-stu-id="f8ea0-116">Path Animation Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
- [<span data-ttu-id="f8ea0-117">경로 애니메이션 방법 항목</span><span class="sxs-lookup"><span data-stu-id="f8ea0-117">Path Animation How-to Topics</span></span>](path-animation-how-to-topics.md)
