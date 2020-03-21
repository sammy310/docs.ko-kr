---
title: '방법: 현재 위치에서 요소가 회전하도록 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], spinning elements
- spinning elements [WPF]
ms.assetid: 1f011976-8b07-4c31-9faf-019e0ddaa24c
ms.openlocfilehash: a1b515822391de08ec8ed8ff0ff1f0086874dc02
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112078"
---
# <a name="how-to-make-an-element-spin-in-place"></a><span data-ttu-id="5f312-102">방법: 현재 위치에서 요소가 회전하도록 만들기</span><span class="sxs-lookup"><span data-stu-id="5f312-102">How to: Make an Element Spin in Place</span></span>
<span data-ttu-id="5f312-103">이 예제에서는 <xref:System.Windows.Media.RotateTransform> a 및 를 사용하여 요소 <xref:System.Windows.Media.Animation.DoubleAnimation>회전을 만드는 방법을 보여 주었습니다.</span><span class="sxs-lookup"><span data-stu-id="5f312-103">This example shows how to make an element spin by using a <xref:System.Windows.Media.RotateTransform> and a <xref:System.Windows.Media.Animation.DoubleAnimation>.</span></span>  
  
 <span data-ttu-id="5f312-104">다음 예제는 <xref:System.Windows.Media.RotateTransform> 요소의 <xref:System.Windows.UIElement.RenderTransform%2A> 속성에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f312-104">The following example applies the <xref:System.Windows.Media.RotateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of the element.</span></span> <span data-ttu-id="5f312-105">이 예제에서는 <xref:System.Windows.Media.Animation.DoubleAnimation> a를 사용하여 <xref:System.Windows.Media.RotateTransform.Angle%2A> 의 <xref:System.Windows.Media.RotateTransform>애니메이션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5f312-105">The example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the <xref:System.Windows.Media.RotateTransform.Angle%2A> of the <xref:System.Windows.Media.RotateTransform>.</span></span> <span data-ttu-id="5f312-106">요소를 제자리에 회전시키기 위해 예제에서는 <xref:System.Windows.UIElement.RenderTransformOrigin%2A> 요소의 속성을 점(0.5, 0.5)으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5f312-106">To make the element spin in place, the example sets the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property of the element to the point (0.5, 0.5).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5f312-107">예제</span><span class="sxs-lookup"><span data-stu-id="5f312-107">Example</span></span>  
 [!code-xaml[transformanimations_snip#11](~/samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/RotateAboutCenterExample.xaml#11)]  
  
 <span data-ttu-id="5f312-108">더 많은 변환 예제가 포함된 전체 샘플의 경우 [2D 변환 샘플을](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5f312-108">For the complete sample, which includes more transformation examples, see [2D Transforms Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f312-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5f312-109">See also</span></span>

- [<span data-ttu-id="5f312-110">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="5f312-110">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="5f312-111">Transform 개요</span><span class="sxs-lookup"><span data-stu-id="5f312-111">Transforms Overview</span></span>](transforms-overview.md)
