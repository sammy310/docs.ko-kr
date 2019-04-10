---
title: '방법: BorderThickness 값에 애니메이션 효과 주기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- border thickness [WPF], animating changes to
- animation [WPF], changes to border thickness
ms.assetid: fd021978-f74b-4e7b-a7f7-3987dcad9e0f
ms.openlocfilehash: 10e177d1f6d6add4638ce14af900e75d7e363890
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59150737"
---
# <a name="how-to-animate-a-borderthickness-value"></a><span data-ttu-id="48492-102">방법: BorderThickness 값에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="48492-102">How to: Animate a BorderThickness Value</span></span>
<span data-ttu-id="48492-103">사용 하 여 테두리의 두께에 대 한 변경을 애니메이션화 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Animation.ThicknessAnimation> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="48492-103">This example shows how to animate changes to the thickness of a border by using the <xref:System.Windows.Media.Animation.ThicknessAnimation> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="48492-104">예제</span><span class="sxs-lookup"><span data-stu-id="48492-104">Example</span></span>  
 <span data-ttu-id="48492-105">다음 예제를 사용 하 여 테두리의 두께 애니메이션을 적용 <xref:System.Windows.Media.Animation.ThicknessAnimation>합니다.</span><span class="sxs-lookup"><span data-stu-id="48492-105">The following example animates the thickness of a border by using <xref:System.Windows.Media.Animation.ThicknessAnimation>.</span></span> <span data-ttu-id="48492-106">이 예제에서는 사용 합니다 <xref:System.Windows.Controls.Border.BorderThickness%2A> 속성의 <xref:System.Windows.Controls.Border>합니다.</span><span class="sxs-lookup"><span data-stu-id="48492-106">The example uses the <xref:System.Windows.Controls.Border.BorderThickness%2A> property of <xref:System.Windows.Controls.Border>.</span></span>  
  
 [!code-csharp[BasicAnimations_snip#ThicknessAnimationWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/ThicknessAnimationExample.cs#thicknessanimationwholepage)]
 [!code-vb[BasicAnimations_snip#ThicknessAnimationWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/ThicknessAnimationExample.vb#thicknessanimationwholepage)]  
  
 <span data-ttu-id="48492-107">전체 샘플을 참조 하세요 [애니메이션 예제 갤러리](https://go.microsoft.com/fwlink/?LinkID=159969)합니다.</span><span class="sxs-lookup"><span data-stu-id="48492-107">For the complete sample, see [Animation Example Gallery](https://go.microsoft.com/fwlink/?LinkID=159969).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48492-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="48492-108">See also</span></span>

- <xref:System.Windows.Media.Animation.ThicknessAnimation>
- <xref:System.Windows.Controls.Border.BorderThickness%2A>
- <xref:System.Windows.Controls.Border>
- [<span data-ttu-id="48492-109">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="48492-109">Animation Overview</span></span>](../graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="48492-110">애니메이션 및 타이밍 방법 항목</span><span class="sxs-lookup"><span data-stu-id="48492-110">Animation and Timing How-to Topics</span></span>](../graphics-multimedia/animation-and-timing-how-to-topics.md)
- [<span data-ttu-id="48492-111">키 프레임을 사용하여 테두리 두께에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="48492-111">Animate the Thickness of a Border by Using Key Frames</span></span>](../graphics-multimedia/how-to-animate-the-thickness-of-a-border-by-using-key-frames.md)
