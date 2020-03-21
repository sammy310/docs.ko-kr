---
title: '방법: 3D 장면에서 재질 속성 에 애니메이션'
ms.date: 03/30/2017
helpviewer_keywords:
- Material properties [WPF], animating in 3D scenes
- animation [WPF], Material properties in 3D scenes
- 3D scenes [WPF], animating Material properties
ms.assetid: 229fd6eb-7401-4992-b0c9-8b28de230c0f
ms.openlocfilehash: db59debcd7558cde52d8604cb04c8c4e68921825
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112195"
---
# <a name="how-to-animate-material-properties-in-a-3d-scene"></a><span data-ttu-id="159e5-102">방법: 3D 장면에서 재질 속성 에 애니메이션</span><span class="sxs-lookup"><span data-stu-id="159e5-102">How to: Animate Material Properties in a 3D Scene</span></span>
<span data-ttu-id="159e5-103">이 예제에서는 3D 모델에 <xref:System.Windows.Media.Brush.Opacity%2A> 적용된 <xref:System.Windows.Media.Media3D.Material> 속성에 애니메이션하는 방법을 보여 주며, 이 예제에서는 3D 모델에 적용된 속성을 애니메이션하는 방법을 보여 주며, 이 예제에서는</span><span class="sxs-lookup"><span data-stu-id="159e5-103">This example shows how to animate the <xref:System.Windows.Media.Brush.Opacity%2A> property of the <xref:System.Windows.Media.Media3D.Material> applied to a 3D model.</span></span>  
  
 <span data-ttu-id="159e5-104">다음 코드 예제는 <xref:System.Windows.Media.LinearGradientBrush> 3D <xref:System.Windows.Media.Media3D.Material> 개체에 적용된 것으로 사용되는 것을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="159e5-104">The following code example defines the <xref:System.Windows.Media.LinearGradientBrush> used as the <xref:System.Windows.Media.Media3D.Material> applied to the 3D object.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline1)]  
  
 <span data-ttu-id="159e5-105">이 <xref:System.Windows.Media.Brush.Opacity%2A> <xref:System.Windows.Media.LinearGradientBrush> 속성은 아래 코드 예제를 사용하여 애니메이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="159e5-105">The <xref:System.Windows.Media.Brush.Opacity%2A> property of this <xref:System.Windows.Media.LinearGradientBrush> is animated using the code example below.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline2)]  
  
## <a name="example"></a><span data-ttu-id="159e5-106">예제</span><span class="sxs-lookup"><span data-stu-id="159e5-106">Example</span></span>  
 <span data-ttu-id="159e5-107">다음 코드에는 전체 샘플을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="159e5-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="159e5-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="159e5-108">See also</span></span>

- [<span data-ttu-id="159e5-109">3D 장면 만들기</span><span class="sxs-lookup"><span data-stu-id="159e5-109">Create a 3D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="159e5-110">3D 그래픽 개요</span><span class="sxs-lookup"><span data-stu-id="159e5-110">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
