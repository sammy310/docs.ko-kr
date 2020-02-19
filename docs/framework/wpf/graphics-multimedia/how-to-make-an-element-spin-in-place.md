---
title: '방법: 현재 위치에서 요소가 회전하도록 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], spinning elements
- spinning elements [WPF]
ms.assetid: 1f011976-8b07-4c31-9faf-019e0ddaa24c
ms.openlocfilehash: 2e72389a11e48629c2763fcbd9f7b1945ffff5dd
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452794"
---
# <a name="how-to-make-an-element-spin-in-place"></a><span data-ttu-id="05815-102">방법: 현재 위치에서 요소가 회전하도록 만들기</span><span class="sxs-lookup"><span data-stu-id="05815-102">How to: Make an Element Spin in Place</span></span>
<span data-ttu-id="05815-103">이 예제에서는 <xref:System.Windows.Media.RotateTransform> 및 <xref:System.Windows.Media.Animation.DoubleAnimation>를 사용 하 여 요소를 회전 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="05815-103">This example shows how to make an element spin by using a <xref:System.Windows.Media.RotateTransform> and a <xref:System.Windows.Media.Animation.DoubleAnimation>.</span></span>  
  
 <span data-ttu-id="05815-104">다음 예에서는 <xref:System.Windows.Media.RotateTransform>를 요소의 <xref:System.Windows.UIElement.RenderTransform%2A> 속성에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="05815-104">The following example applies the <xref:System.Windows.Media.RotateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of the element.</span></span> <span data-ttu-id="05815-105">이 예제에서는 <xref:System.Windows.Media.Animation.DoubleAnimation>를 사용 하 여 <xref:System.Windows.Media.RotateTransform><xref:System.Windows.Media.RotateTransform.Angle%2A>에 애니메이션 효과를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="05815-105">The example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the <xref:System.Windows.Media.RotateTransform.Angle%2A> of the <xref:System.Windows.Media.RotateTransform>.</span></span> <span data-ttu-id="05815-106">요소가 현재 위치에서 회전 하도록 하기 위해이 예제에서는 요소의 <xref:System.Windows.UIElement.RenderTransformOrigin%2A> 속성을 point (0.5, 0.5)로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="05815-106">To make the element spin in place, the example sets the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property of the element to the point (0.5, 0.5).</span></span>  
  
## <a name="example"></a><span data-ttu-id="05815-107">예제</span><span class="sxs-lookup"><span data-stu-id="05815-107">Example</span></span>  
 [!code-xaml[transformanimations_snip#11](~/samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/RotateAboutCenterExample.xaml#11)]  
  
 <span data-ttu-id="05815-108">더 많은 변환 예제를 포함 하는 전체 샘플은 [2 차원 변환 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="05815-108">For the complete sample, which includes more transformation examples, see [2-D Transforms Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05815-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="05815-109">See also</span></span>

- [<span data-ttu-id="05815-110">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="05815-110">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="05815-111">Transform 개요</span><span class="sxs-lookup"><span data-stu-id="05815-111">Transforms Overview</span></span>](transforms-overview.md)
