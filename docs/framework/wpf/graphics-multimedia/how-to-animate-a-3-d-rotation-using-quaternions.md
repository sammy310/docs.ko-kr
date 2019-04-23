---
title: '방법: 4원수를 사용하여 3차원 회전에 애니메이션 효과 주기'
ms.date: 03/30/2017
helpviewer_keywords:
- quaternions [WPF]
- animation [WPF], 3-D translations [WPF], with quaternions
- 3-D translations [WPF], animating [WPF], with quaternions
ms.assetid: adca9cb1-066b-4de8-abbb-6b4007579ee7
ms.openlocfilehash: d994ac2ae67fd366f27f123d5bd15f14d5ac7abe
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59183224"
---
# <a name="how-to-animate-a-3-d-rotation-using-quaternions"></a><span data-ttu-id="c511c-102">방법: 4원수를 사용하여 3차원 회전에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="c511c-102">How to: Animate a 3-D Rotation Using Quaternions</span></span>
<span data-ttu-id="c511c-103">이 예제에는 4 원수를 사용 하 여 3 차원 개체를 회전에 애니메이션을 적용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c511c-103">This example shows how to animate a rotation of a 3-D object using quaternions.</span></span>  
  
 <span data-ttu-id="c511c-104">아래 코드를 <xref:System.Windows.Media.Media3D.QuaternionRotation3D> 에 대 한 값으로 사용 합니다 <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> 의 속성을 <xref:System.Windows.Media.Media3D.RotateTransform3D>.</span><span class="sxs-lookup"><span data-stu-id="c511c-104">The code below shows a <xref:System.Windows.Media.Media3D.QuaternionRotation3D> used as the value for the <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> property of a <xref:System.Windows.Media.Media3D.RotateTransform3D>.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline1)]  
  
 <span data-ttu-id="c511c-105">이 <xref:System.Windows.Media.Media3D.QuaternionRotation3D> 사용 하 여 애니메이션 효과가 적용 됩니다는 <xref:System.Windows.Media.Animation.QuaternionAnimation> 내에서 <xref:System.Windows.Media.Animation.Storyboard> 아래 코드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c511c-105">This <xref:System.Windows.Media.Media3D.QuaternionRotation3D> is animated with a <xref:System.Windows.Media.Animation.QuaternionAnimation> within a <xref:System.Windows.Media.Animation.Storyboard> using the code below.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline2)]  
  
## <a name="example"></a><span data-ttu-id="c511c-106">예제</span><span class="sxs-lookup"><span data-stu-id="c511c-106">Example</span></span>  
 <span data-ttu-id="c511c-107">다음 코드에는 전체 샘플을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c511c-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="c511c-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="c511c-108">See also</span></span>

- [<span data-ttu-id="c511c-109">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="c511c-109">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="c511c-110">3차원 장면 만들기</span><span class="sxs-lookup"><span data-stu-id="c511c-110">Create a 3-D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="c511c-111">3차원 그래픽 개요</span><span class="sxs-lookup"><span data-stu-id="c511c-111">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="c511c-112">Transform 개요</span><span class="sxs-lookup"><span data-stu-id="c511c-112">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="c511c-113">Storyboard를 사용하여 3차원 회전에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="c511c-113">Animate a 3-D Rotation Using Storyboards</span></span>](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [<span data-ttu-id="c511c-114">Rotation3DAnimation을 사용하여 3차원 회전에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="c511c-114">Animate a 3-D Rotation Using Rotation3DAnimation</span></span>](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
