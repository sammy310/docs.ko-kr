---
title: '방법: 3차원 장면의 Material 속성에 애니메이션 효과 주기'
ms.date: 03/30/2017
helpviewer_keywords:
- Material properties [WPF], animating in 3-D scenes
- animation [WPF], Material properties in 3-D scenes
- 3-D scenes [WPF], animating Material properties
ms.assetid: 229fd6eb-7401-4992-b0c9-8b28de230c0f
ms.openlocfilehash: 8dfd7f01b87e2becfbcf57544ec4f8340cf8d5cc
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2019
ms.locfileid: "67662548"
---
# <a name="how-to-animate-material-properties-in-a-3-d-scene"></a><span data-ttu-id="59113-102">방법: 3차원 장면의 Material 속성에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="59113-102">How to: Animate Material Properties in a 3-D Scene</span></span>
<span data-ttu-id="59113-103">애니메이션을 적용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Brush.Opacity%2A> 의 속성을 <xref:System.Windows.Media.Media3D.Material> 3d 모델에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="59113-103">This example shows how to animate the <xref:System.Windows.Media.Brush.Opacity%2A> property of the <xref:System.Windows.Media.Media3D.Material> applied to a 3-D model.</span></span>  
  
 <span data-ttu-id="59113-104">다음 코드 예제에서는 정의 <xref:System.Windows.Media.LinearGradientBrush> 받았던는 <xref:System.Windows.Media.Media3D.Material> 3D 개체에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="59113-104">The following code example defines the <xref:System.Windows.Media.LinearGradientBrush> used as the <xref:System.Windows.Media.Media3D.Material> applied to the 3D object.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline1)]  
  
 <span data-ttu-id="59113-105">합니다 <xref:System.Windows.Media.Brush.Opacity%2A> 속성을이 <xref:System.Windows.Media.LinearGradientBrush> 아래 코드 예제를 사용 하 여 애니메이션 효과가 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="59113-105">The <xref:System.Windows.Media.Brush.Opacity%2A> property of this <xref:System.Windows.Media.LinearGradientBrush> is animated using the code example below.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline2)]  
  
## <a name="example"></a><span data-ttu-id="59113-106">예제</span><span class="sxs-lookup"><span data-stu-id="59113-106">Example</span></span>  
 <span data-ttu-id="59113-107">다음 코드에는 전체 샘플을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="59113-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="59113-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="59113-108">See also</span></span>

- [<span data-ttu-id="59113-109">3차원 장면 만들기</span><span class="sxs-lookup"><span data-stu-id="59113-109">Create a 3-D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="59113-110">3차원 그래픽 개요</span><span class="sxs-lookup"><span data-stu-id="59113-110">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
