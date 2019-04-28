---
title: '방법: PointAnimation을 사용하여 개체 위치에 애니메이션 효과 주기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], animation
- animation [WPF], PointAnimation
ms.assetid: 42310977-cc90-438a-8a47-0345898e01be
ms.openlocfilehash: 1ef3f77e551affaa7e61d2aabf95f10c29275417
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61651352"
---
# <a name="how-to-animate-the-position-of-an-object-by-using-pointanimation"></a><span data-ttu-id="ab225-102">방법: PointAnimation을 사용하여 개체 위치에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="ab225-102">How to: Animate the Position of an Object by Using PointAnimation</span></span>
<span data-ttu-id="ab225-103">사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Animation.PointAnimation> 클래스를 따라 개체에 애니메이션 효과 주기는 <xref:System.Windows.Shapes.Path>합니다.</span><span class="sxs-lookup"><span data-stu-id="ab225-103">This example shows how to use the <xref:System.Windows.Media.Animation.PointAnimation> class to animate an object along a <xref:System.Windows.Shapes.Path>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ab225-104">예제</span><span class="sxs-lookup"><span data-stu-id="ab225-104">Example</span></span>  
 <span data-ttu-id="ab225-105">다음 예제를 따라 타원을 이동는 <xref:System.Windows.Shapes.Path> 다른 화면의 한 점에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab225-105">The following example moves an ellipse along a <xref:System.Windows.Shapes.Path> from one point on the screen to another.</span></span> <span data-ttu-id="ab225-106">예제 애니메이션의 위치는 <xref:System.Windows.Media.EllipseGeometry> 를 사용 하 여 <xref:System.Windows.Media.Animation.PointAnimation> 애니메이션 효과를 주는 <xref:System.Windows.Media.EllipseGeometry.Center%2A> 속성.</span><span class="sxs-lookup"><span data-stu-id="ab225-106">The example animates the position of an <xref:System.Windows.Media.EllipseGeometry> by using <xref:System.Windows.Media.Animation.PointAnimation> to animate the <xref:System.Windows.Media.EllipseGeometry.Center%2A> property.</span></span>  
  
 [!code-csharp[BasicAnimations_snip#PointAnimationWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/PointAnimationExample.cs#pointanimationwholepage)]
 [!code-vb[BasicAnimations_snip#PointAnimationWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/PointAnimationExample.vb#pointanimationwholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="ab225-107">참고자료</span><span class="sxs-lookup"><span data-stu-id="ab225-107">See also</span></span>

- <xref:System.Windows.Media.Animation.PointAnimation>
- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.EllipseGeometry>
- <xref:System.Windows.Media.EllipseGeometry.Center%2A>
- [<span data-ttu-id="ab225-108">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="ab225-108">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="ab225-109">그래픽 및 멀티미디어</span><span class="sxs-lookup"><span data-stu-id="ab225-109">Graphics and Multimedia</span></span>](index.md)
- [<span data-ttu-id="ab225-110">그래픽 방법 항목</span><span class="sxs-lookup"><span data-stu-id="ab225-110">Graphics How-to Topics</span></span>](graphics-how-to-topics.md)
- [<span data-ttu-id="ab225-111">애니메이션 및 타이밍 방법 항목</span><span class="sxs-lookup"><span data-stu-id="ab225-111">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
