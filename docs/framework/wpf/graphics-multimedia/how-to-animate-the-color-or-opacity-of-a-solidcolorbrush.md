---
title: '방법: SolidColorBrush의 색 또는 불투명도에 애니메이션 효과 적용'
ms.date: 03/30/2017
helpviewer_keywords:
- SolidColorBrush [WPF], animating color of
- colors [WPF], animating
- opacity [WPF], animating
- animation [WPF], color of SolidColorBrush
- animation [WPF], opacity of SolidColorBrush
- SolidColorBrush [WPF], animating opacity of
ms.assetid: d9154354-843f-4713-bad1-35bb0ba6eaeb
ms.openlocfilehash: 08b85935e0cb1ababd1fb63b9d02518ea3fcfa17
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452885"
---
# <a name="how-to-animate-the-color-or-opacity-of-a-solidcolorbrush"></a><span data-ttu-id="a07ac-102">방법: SolidColorBrush의 색 또는 불투명도에 애니메이션 효과 적용</span><span class="sxs-lookup"><span data-stu-id="a07ac-102">How to: Animate the Color or Opacity of a SolidColorBrush</span></span>
<span data-ttu-id="a07ac-103">이 예제에서는 <xref:System.Windows.Media.SolidColorBrush>의 <xref:System.Windows.Media.SolidColorBrush.Color%2A> 및 <xref:System.Windows.Media.Brush.Opacity%2A>에 애니메이션 효과를 주는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a07ac-103">This example shows how to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> and <xref:System.Windows.Media.Brush.Opacity%2A> of a <xref:System.Windows.Media.SolidColorBrush>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a07ac-104">예제</span><span class="sxs-lookup"><span data-stu-id="a07ac-104">Example</span></span>  
 <span data-ttu-id="a07ac-105">다음 예제에서는 세 가지 애니메이션을 사용 하 여 <xref:System.Windows.Media.SolidColorBrush.Color%2A> 및 <xref:System.Windows.Media.SolidColorBrush>의 <xref:System.Windows.Media.Brush.Opacity%2A>에 애니메이션 효과를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a07ac-105">The following example uses three animations to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> and <xref:System.Windows.Media.Brush.Opacity%2A> of a <xref:System.Windows.Media.SolidColorBrush>.</span></span>  
  
- <span data-ttu-id="a07ac-106">첫 번째 애니메이션 인 <xref:System.Windows.Media.Animation.ColorAnimation>는 마우스를 사각형 안으로 가져갈 때 브러시의 색을 <xref:System.Windows.Media.Colors.Gray%2A>으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="a07ac-106">The first animation, a <xref:System.Windows.Media.Animation.ColorAnimation>, changes the brush's color to <xref:System.Windows.Media.Colors.Gray%2A> when the mouse enters the rectangle.</span></span>  
  
- <span data-ttu-id="a07ac-107">다음 애니메이션 인 다른 <xref:System.Windows.Media.Animation.ColorAnimation>는 마우스가 사각형을 벗어날 때 브러시의 색을 <xref:System.Windows.Media.Colors.Orange%2A>으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="a07ac-107">The next animation, another <xref:System.Windows.Media.Animation.ColorAnimation>, changes the brush's color to <xref:System.Windows.Media.Colors.Orange%2A> when the mouse leaves the rectangle.</span></span>  
  
- <span data-ttu-id="a07ac-108">최종 애니메이션 <xref:System.Windows.Media.Animation.DoubleAnimation>왼쪽 마우스 단추를 누르면 브러시의 불투명도가 0.0로 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a07ac-108">The final animation, a <xref:System.Windows.Media.Animation.DoubleAnimation>, changes the brush's opacity to 0.0 when the left mouse button is pressed.</span></span>  
  
 [!code-csharp[brushanimations_snip#SolidColorBrushAnimationExample](~/samples/snippets/csharp/VS_Snippets_Wpf/brushanimations_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushanimationexample)]  
  
 <span data-ttu-id="a07ac-109">여러 브러시 형식에 애니메이션 효과를 주는 방법을 보여 주는 전체 샘플을 보려면 [브러시 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a07ac-109">For a more complete sample, which shows how to animate different types of brushes, see the [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span></span> <span data-ttu-id="a07ac-110">애니메이션에 대 한 자세한 내용은 [애니메이션 개요](animation-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a07ac-110">For more information about animation, see the [Animation Overview](animation-overview.md).</span></span>  
  
 <span data-ttu-id="a07ac-111">다른 애니메이션 예제와의 일관성을 위해이 예제의 코드 버전에서는 <xref:System.Windows.Media.Animation.Storyboard> 개체를 사용 하 여 애니메이션을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a07ac-111">For consistency with other animation examples, the code versions of this example use a <xref:System.Windows.Media.Animation.Storyboard> object to apply their animations.</span></span> <span data-ttu-id="a07ac-112">그러나 코드에서 단일 애니메이션을 적용 하는 경우 <xref:System.Windows.Media.Animation.Storyboard>를 사용 하는 대신 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 메서드를 사용 하는 것이 더 간단 합니다.</span><span class="sxs-lookup"><span data-stu-id="a07ac-112">However, when applying a single animation in code, it's simpler to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method instead of using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="a07ac-113">예제를 보려면 [Storyboard를 사용하지 않고 속성에 애니메이션 효과 주기](how-to-animate-a-property-without-using-a-storyboard.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a07ac-113">For an example, see [Animate a Property Without Using a Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a07ac-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a07ac-114">See also</span></span>

- [<span data-ttu-id="a07ac-115">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="a07ac-115">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="a07ac-116">Storyboard 개요</span><span class="sxs-lookup"><span data-stu-id="a07ac-116">Storyboards Overview</span></span>](storyboards-overview.md)
- [<span data-ttu-id="a07ac-117">브러시 샘플</span><span class="sxs-lookup"><span data-stu-id="a07ac-117">Brushes Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)
