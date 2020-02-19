---
title: '방법: 경로를 따라 개체에 애니메이션 효과 주기(Double 애니메이션)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (double animation)
- double animation [WPF]
ms.assetid: 5a3c4a99-f303-42ad-a52a-e4794bb1798e
ms.openlocfilehash: 084caac26fd68b6914ec3858652ec44557a0dbd7
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452859"
---
# <a name="how-to-animate-an-object-along-a-path-double-animation"></a><span data-ttu-id="aee8f-102">방법: 경로를 따라 개체에 애니메이션 효과 주기(Double 애니메이션)</span><span class="sxs-lookup"><span data-stu-id="aee8f-102">How to: Animate an Object Along a Path (Double Animation)</span></span>
<span data-ttu-id="aee8f-103">이 예제에서는 <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> 클래스를 사용 하 여 <xref:System.Windows.Media.PathGeometry>에서 정의한 경로를 따라 개체를 이동 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="aee8f-103">This example shows how to use the <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> class to move an object along a path defined by a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aee8f-104">예제</span><span class="sxs-lookup"><span data-stu-id="aee8f-104">Example</span></span>  
 <span data-ttu-id="aee8f-105">다음 예제에서는 두 개의 <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> 개체를 사용 하 여 기하학적 경로를 따라 사각형을 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="aee8f-105">The following example uses two <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> objects to move a rectangle along a geometric path:</span></span>  
  
- <span data-ttu-id="aee8f-106">첫 번째 <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>는 사각형에 적용 되는 <xref:System.Windows.Media.TranslateTransform> <xref:System.Windows.Media.TranslateTransform.X%2A>에 애니메이션 효과를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="aee8f-106">The first <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animates the <xref:System.Windows.Media.TranslateTransform.X%2A> of the <xref:System.Windows.Media.TranslateTransform> applied to the rectangle.</span></span> <span data-ttu-id="aee8f-107">이를 통해 사각형이 경로를 따라 가로로 이동하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aee8f-107">It makes the rectangle move horizontally along the path.</span></span>  
  
- <span data-ttu-id="aee8f-108">두 번째 <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> 사각형에 적용 되는 <xref:System.Windows.Media.TranslateTransform> <xref:System.Windows.Media.TranslateTransform.Y%2A>에 애니메이션 효과를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="aee8f-108">The second <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animates the <xref:System.Windows.Media.TranslateTransform.Y%2A> of the <xref:System.Windows.Media.TranslateTransform> applied to the rectangle.</span></span> <span data-ttu-id="aee8f-109">이를 통해 사각형이 경로를 따라 세로로 이동하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aee8f-109">It makes the rectangle move vertically along the path.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#DoubleAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/doubleanimationusingpathexample.xaml#doubleanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#DoubleAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/DoubleAnimationUsingPathExample.cs#doubleanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#DoubleAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/DoubleAnimationUsingPathExample.vb#doubleanimationusingpathwholepage)]  
  
 <span data-ttu-id="aee8f-110">전체 샘플은 [경로 애니메이션 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="aee8f-110">For the complete sample, see [Path Animation Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).</span></span>  
  
 <span data-ttu-id="aee8f-111">기하학적 경로를 사용 하 여 개체를 이동 하는 또 다른 방법은 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 개체를 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="aee8f-111">Another way to move an object using a geometric path is to use a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object.</span></span> <span data-ttu-id="aee8f-112">예를 들어 경로를 [따라 개체에 애니메이션 효과 주기 (Matrix 애니메이션)](how-to-animate-an-object-along-a-path-matrix-animation.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="aee8f-112">For an example, see [Animate an Object Along a Path (Matrix Animation)](how-to-animate-an-object-along-a-path-matrix-animation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aee8f-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aee8f-113">See also</span></span>

- [<span data-ttu-id="aee8f-114">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="aee8f-114">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="aee8f-115">경로 애니메이션 방법 항목</span><span class="sxs-lookup"><span data-stu-id="aee8f-115">Path Animation How-to Topics</span></span>](path-animation-how-to-topics.md)
