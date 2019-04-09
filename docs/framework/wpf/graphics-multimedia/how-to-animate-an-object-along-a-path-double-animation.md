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
ms.openlocfilehash: 54f345bbe6b513e3593cbf45ba190d4a44228424
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59101447"
---
# <a name="how-to-animate-an-object-along-a-path-double-animation"></a><span data-ttu-id="0a03c-102">방법: 경로를 따라 개체에 애니메이션 효과 주기(Double 애니메이션)</span><span class="sxs-lookup"><span data-stu-id="0a03c-102">How to: Animate an Object Along a Path (Double Animation)</span></span>
<span data-ttu-id="0a03c-103">사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> 정의한 경로 따라 개체를 이동 하는 클래스는 <xref:System.Windows.Media.PathGeometry>합니다.</span><span class="sxs-lookup"><span data-stu-id="0a03c-103">This example shows how to use the <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> class to move an object along a path defined by a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0a03c-104">예제</span><span class="sxs-lookup"><span data-stu-id="0a03c-104">Example</span></span>  
 <span data-ttu-id="0a03c-105">다음 예제에서는 두 <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> 개체 기하학적 경로 따라 사각형을 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a03c-105">The following example uses two <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> objects to move a rectangle along a geometric path:</span></span>  
  
-   <span data-ttu-id="0a03c-106">첫 번째 <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> 애니메이션을 적용 합니다 <xref:System.Windows.Media.TranslateTransform.X%2A> 의 <xref:System.Windows.Media.TranslateTransform> 사각형에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a03c-106">The first <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animates the <xref:System.Windows.Media.TranslateTransform.X%2A> of the <xref:System.Windows.Media.TranslateTransform> applied to the rectangle.</span></span> <span data-ttu-id="0a03c-107">이를 통해 사각형이 경로를 따라 가로로 이동하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a03c-107">It makes the rectangle move horizontally along the path.</span></span>  
  
-   <span data-ttu-id="0a03c-108">두 번째 <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> 애니메이션을 적용 합니다 <xref:System.Windows.Media.TranslateTransform.Y%2A> 의 <xref:System.Windows.Media.TranslateTransform> 사각형에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a03c-108">The second <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animates the <xref:System.Windows.Media.TranslateTransform.Y%2A> of the <xref:System.Windows.Media.TranslateTransform> applied to the rectangle.</span></span> <span data-ttu-id="0a03c-109">이를 통해 사각형이 경로를 따라 세로로 이동하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a03c-109">It makes the rectangle move vertically along the path.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#DoubleAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/doubleanimationusingpathexample.xaml#doubleanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#DoubleAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/DoubleAnimationUsingPathExample.cs#doubleanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#DoubleAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/DoubleAnimationUsingPathExample.vb#doubleanimationusingpathwholepage)]  
  
 <span data-ttu-id="0a03c-110">전체 샘플을 참조 하세요 [경로 애니메이션 샘플](https://go.microsoft.com/fwlink/?LinkID=160028)합니다.</span><span class="sxs-lookup"><span data-stu-id="0a03c-110">For the complete sample, see [Path Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160028).</span></span>  
  
 <span data-ttu-id="0a03c-111">기하학적 경로 사용 하 여 개체를 이동 하는 또 다른 방법은 사용 하는 것을 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="0a03c-111">Another way to move an object using a geometric path is to use a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object.</span></span> <span data-ttu-id="0a03c-112">예를 들어 참조 [는 경로 따라 개체 (매트릭스 애니메이션)에 애니메이션 효과 주기](how-to-animate-an-object-along-a-path-matrix-animation.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0a03c-112">For an example, see [Animate an Object Along a Path (Matrix Animation)](how-to-animate-an-object-along-a-path-matrix-animation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a03c-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="0a03c-113">See also</span></span>

- [<span data-ttu-id="0a03c-114">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="0a03c-114">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="0a03c-115">경로 애니메이션 방법 항목</span><span class="sxs-lookup"><span data-stu-id="0a03c-115">Path Animation How-to Topics</span></span>](path-animation-how-to-topics.md)
