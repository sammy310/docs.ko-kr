---
title: '방법: 텍스트에 애니메이션 적용'
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], animations
- animation [WPF], text
ms.assetid: eec3d26c-0a21-420f-8012-671621c47089
ms.openlocfilehash: ed2f3beb904f724ac93e2c4033aa6b2eb3fa1290
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174630"
---
# <a name="how-to-apply-animations-to-text"></a><span data-ttu-id="f9d11-102">방법: 텍스트에 애니메이션 적용</span><span class="sxs-lookup"><span data-stu-id="f9d11-102">How to: Apply Animations to Text</span></span>
<span data-ttu-id="f9d11-103">애니메이션은 애플리케이션의 텍스트 모양과 표시를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9d11-103">Animations can alter the display and appearance of text in your application.</span></span> <span data-ttu-id="f9d11-104">다음 예제에서는 컨트롤의 텍스트 표시에 영향을 주는 다양한 <xref:System.Windows.Controls.TextBlock> 유형의 애니메이션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d11-104">The following examples use different types of animations to affect the display of text in a <xref:System.Windows.Controls.TextBlock> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9d11-105">예제</span><span class="sxs-lookup"><span data-stu-id="f9d11-105">Example</span></span>  
 <span data-ttu-id="f9d11-106">다음 예제에서는 <xref:System.Windows.Media.Animation.DoubleAnimation> a를 사용하여 텍스트 블록의 너비를 애니메이션합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d11-106">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the width of the text block.</span></span> <span data-ttu-id="f9d11-107">10초 동안 너비 값을 텍스트 블록의 너비에서 0으로 변경한 후 다시 너비 값을 반대로 변경하여 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d11-107">The width value changes from the width of the text block to 0 over a duration of 10 seconds, and then reverses the width values and continues.</span></span> <span data-ttu-id="f9d11-108">이러한 형식의 애니메이션은 지우기 효과를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d11-108">This type of animation creates a wipe effect.</span></span>  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample1)]  
  
 <span data-ttu-id="f9d11-109">다음 예제에서는 <xref:System.Windows.Media.Animation.DoubleAnimation> a를 사용하여 텍스트 블록의 불투명도를 애니메이션합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d11-109">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the opacity of the text block.</span></span> <span data-ttu-id="f9d11-110">5초 동안 불투명도 값을 1.0에서 0으로 변경한 다음 불투명 값을 반대로 변경하고 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d11-110">The opacity value changes from 1.0 to 0 over a duration of 5 seconds, and then reverses the opacity values and continues.</span></span>  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample2)]  
  
 <span data-ttu-id="f9d11-111">다음 다이어그램은 <xref:System.Windows.Controls.TextBlock> 컨트롤이 `1.00` `0.00` <xref:System.Windows.Media.Animation.Timeline.Duration%2A>에 의해 정의된 5초 간격동안 불투명도를 변경하는 효과를 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="f9d11-111">The following diagram shows the effect of the <xref:System.Windows.Controls.TextBlock> control changing its opacity from `1.00` to `0.00` during the 5-second interval defined by the <xref:System.Windows.Media.Animation.Timeline.Duration%2A>.</span></span>  
  
 ![불투명도를 1.00에서 0.00으로 변경하는 텍스트입니다.](./media/how-to-apply-animations-to-text/faded-text-opacity-change.png)  

 <span data-ttu-id="f9d11-113">다음 예제에서는 <xref:System.Windows.Media.Animation.ColorAnimation> a를 사용하여 텍스트 블록의 전경 색상을 애니메이션합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d11-113">The following example uses a <xref:System.Windows.Media.Animation.ColorAnimation> to animate the foreground color of the text block.</span></span> <span data-ttu-id="f9d11-114">전경색 값을 5초 동안 한 색상에서 두 번째 색상으로 변경한 다음 색상 값을 반대로 변경하고 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d11-114">The foreground color value changes from one color to a second color over a duration of 5 seconds, and then reverses the color values and continues.</span></span>  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample3)]  
  
 <span data-ttu-id="f9d11-115">다음 예제에서는 <xref:System.Windows.Media.Animation.DoubleAnimation> a를 사용하여 텍스트 블록을 회전시킵니다.</span><span class="sxs-lookup"><span data-stu-id="f9d11-115">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to rotate the text block.</span></span> <span data-ttu-id="f9d11-116">텍스트 블록은 20초 동안 전체 회전을 수행한 다음 회전을 계속 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="f9d11-116">The text block performs a full rotation over a duration of 20 seconds, and then continues to repeat the rotation.</span></span>  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample4](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample4)]  
  
## <a name="see-also"></a><span data-ttu-id="f9d11-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f9d11-117">See also</span></span>

- [<span data-ttu-id="f9d11-118">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="f9d11-118">Animation Overview</span></span>](../graphics-multimedia/animation-overview.md)
