---
title: '방법: 쿼터니언을 사용하여 3D 회전 애니메이션'
ms.date: 03/30/2017
helpviewer_keywords:
- quaternions [WPF]
- animation [WPF], 3D translations [WPF], with quaternions
- 3D translations [WPF], animating [WPF], with quaternions
ms.assetid: adca9cb1-066b-4de8-abbb-6b4007579ee7
ms.openlocfilehash: 0d229b0a714cc53459943fae751ab4d4f787d7d8
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112247"
---
# <a name="how-to-animate-a-3d-rotation-using-quaternions"></a><span data-ttu-id="b706d-102">방법: 쿼터니언을 사용하여 3D 회전 애니메이션</span><span class="sxs-lookup"><span data-stu-id="b706d-102">How to: Animate a 3D Rotation Using Quaternions</span></span>
<span data-ttu-id="b706d-103">이 예제에서는 쿼터니언을 사용하여 3D 오브젝트의 회전을 애니메이션하는 방법을 보여 주며, 이 예제에서는 쿼터니언을 사용하여 애니메이션을 사용하는 방법을 보여 주며, 3D 오브젝트의 회전을 애니메이션하는 방법을 보여 주며, 이 예제에서는 쿼터니언을 사용하여 3D 오브젝트의 회전을 애니메이션하는 방법을 보여</span><span class="sxs-lookup"><span data-stu-id="b706d-103">This example shows how to animate a rotation of a 3D object using quaternions.</span></span>  
  
 <span data-ttu-id="b706d-104">아래 코드는 <xref:System.Windows.Media.Media3D.QuaternionRotation3D> <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> <xref:System.Windows.Media.Media3D.RotateTransform3D>에 대한 속성값으로 사용된 값을 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="b706d-104">The code below shows a <xref:System.Windows.Media.Media3D.QuaternionRotation3D> used as the value for the <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> property of a <xref:System.Windows.Media.Media3D.RotateTransform3D>.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline1)]  
  
 <span data-ttu-id="b706d-105">이것은 <xref:System.Windows.Media.Media3D.QuaternionRotation3D> 아래 코드를 <xref:System.Windows.Media.Animation.QuaternionAnimation> <xref:System.Windows.Media.Animation.Storyboard> 사용하여 내에서 애니메이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="b706d-105">This <xref:System.Windows.Media.Media3D.QuaternionRotation3D> is animated with a <xref:System.Windows.Media.Animation.QuaternionAnimation> within a <xref:System.Windows.Media.Animation.Storyboard> using the code below.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline2)]  
  
## <a name="example"></a><span data-ttu-id="b706d-106">예제</span><span class="sxs-lookup"><span data-stu-id="b706d-106">Example</span></span>  
 <span data-ttu-id="b706d-107">다음 코드에는 전체 샘플을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b706d-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="b706d-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b706d-108">See also</span></span>

- [<span data-ttu-id="b706d-109">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="b706d-109">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="b706d-110">3D 장면 만들기</span><span class="sxs-lookup"><span data-stu-id="b706d-110">Create a 3D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="b706d-111">3D 그래픽 개요</span><span class="sxs-lookup"><span data-stu-id="b706d-111">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="b706d-112">Transform 개요</span><span class="sxs-lookup"><span data-stu-id="b706d-112">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="b706d-113">스토리보드를 사용하여 3D 회전 애니메이션</span><span class="sxs-lookup"><span data-stu-id="b706d-113">Animate a 3D Rotation Using Storyboards</span></span>](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [<span data-ttu-id="b706d-114">회전3D애니메이션을 사용하여 3D 회전 애니메이션</span><span class="sxs-lookup"><span data-stu-id="b706d-114">Animate a 3D Rotation Using Rotation3DAnimation</span></span>](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
